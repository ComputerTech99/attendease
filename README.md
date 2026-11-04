# AttendEase – 75% Attendance Planner

A small web app built for the **Computational Thinking as an Engineering Mindset** individual activity (IPS, Jain Deemed-to-be University).

**Live site:** https://computertech99.github.io/attendease/
**Demo video:** https://computertech99.github.io/attendease/assets/demo.mp4

## Problem

Colleges require students to keep at least 75% attendance in every subject. Students track this by hand or not at all, and often discover too late that they are short and cannot sit the exam. AttendEase tells each student, subject by subject:

- their current attendance percentage
- how many classes they can still skip and stay at or above the target, or
- how many classes in a row they must attend to get back to the target.

## Features

- Add, edit and delete subjects (classes held, classes attended)
- Change the required percentage (default 75%)
- Status per subject: Safe, Borderline or At risk, with a progress bar and a marker at the target
- "What if I miss N more?" preview before skipping a class
- Overall attendance and counts of safe and at-risk subjects
- "+ Attended today" / "+ Missed today" buttons to update a subject after each class
- Status legend, plus a red alert listing every subject below the target
- "Copy summary" copies all subjects as text to send to a mentor or parents
- Input checks (empty name, negative numbers, attended greater than held)
- Data saved in the browser (localStorage); dark mode; works on phones

## Algorithm

```
INPUT held, attended, target
pct ← attended / held × 100
IF pct ≥ target THEN
    canSkip ← 0
    WHILE attended / (held + canSkip + 1) × 100 ≥ target
        canSkip ← canSkip + 1
    OUTPUT "You can skip canSkip classes"
ELSE
    mustAttend ← 0
    WHILE (attended + mustAttend) / (held + mustAttend) × 100 < target
        mustAttend ← mustAttend + 1
    OUTPUT "Attend the next mustAttend classes"
END IF
```

## Run locally

Open `index.html` in any browser. No build step and no dependencies.
