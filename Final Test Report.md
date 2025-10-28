# 🧪 Final Group Test Report Template — Word Puzzle Game Plus

**Level:** Intermediate QA | **Week 5:** Test Management

**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-28

## Team Information

| Role | Name | Responsibilities |
|------|------|------------------|
| Test Manager | Prifton Mliwa | Planning, scheduling, coordination, metric tracking |
| Risk Analyst |Peter Adebisi | Risk identification, prioritization, test design linkage |
| Test Executor | Lena Wahu | Execution, evidence capture, defect logging |

## Group Rules

- Each student must belong to only one group.
- Duplicate membership or multiple submissions will result in invalidation.
- Every group member must contribute towards this project

## Project Overview

**System Under Test:** Word Puzzle Game Plus  
**Technology Stack:** HTML, CSS, JavaScript  
**Environment:** Chrome Browser (Desktop)

### Features Under Test

| Feature | Description | Risk Category |
|---------|-------------|---------------|
| Reset Game | Clears score and progress instantly | |
| Leaderboard | Stores top 3 scores in localStorage | |
| Bonus Round | Every 3 puzzles → doubles score | |

## Test Plan

### Objectives

- Validate core game functionality including word scrambling and guessing.
- Verify leaderboard persistence and sorting logic.
- Test bonus round triggering and score doubling mechanism.
- Ensure proper state management during game reset.
- Assess usability and accessibility compliance.

### Scope

**In Scope:**
-  Game initialization and puzzle generation.

- Score calculation with/without hints.

- Leaderboard storage and retrieval.

- Bonus round logic.

- Reset functionality.

- User interface responsiveness.


**Out of Scope:**
- Cross-browser compatibility testing.

- Performance benchmarking.

- Security testing of localStorage.

- Mobile device testing.

- Network interruption handling.

### Tools & Resources
- Testing Framework: Manual testing

- Browser: Chrome 

- Defect Tracking: GitHub Issues

- Documentation: Markdown

- Evidence Capture: Browser screenshots


### Schedule

| Phase | Planned Duration | Actual Duration | Status |
|-------|------------------|-----------------|--------|
|Test Planning | 1 day | 1 day | Completed|
|  Risk Analysis| 1 day | 1 day| Completed |
| Test Case Design |  2 day | 12  day |  Completed|
|  Test Execution | 1 day  | 1 day  | Completed |
| Defect Reporting |1 day |  1 day | Completed | 
|  Final Reporting	| 1 day | 1 day  | inprogress | 


## Risk Analysis

### Risks

| ID | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|:--|:--|:--|:--:|:--:|:--:|:--|
| R1 | Reset Game | Reset button may fail to clear score or progress completely | Medium | High | High | Perform multiple reset operations and verify data state is cleared correctly in each test. |
| R2 | Leaderboard | Scores may not save correctly in localStorage after multiple sessions | High | High | **Critical** | Test storing and retrieving top 3 scores across several browser sessions and refreshes. |
| R3 | Bonus Round | Bonus logic may double wrong score after 3 puzzles | Medium | High | High | Validate arithmetic logic by testing with multiple sequences of puzzles and scores. |
| R4 | Leaderboard | Sorting order may be incorrect (ascending instead of descending) | Medium | Medium | Medium | Test leaderboard with various score values and confirm correct descending order. |
| R5 | UI / Buttons | Buttons may overlap or become unclickable at certain window sizes | Low | Medium | Low | Perform responsive UI tests in Chrome browser at different resolutions. |
| R6 | Reset Game | Reset may still be enabled during active bonus round | Low | High | Medium | Trigger reset mid-bonus round to confirm safe state handling. |
| R7  |	Hint System	| Incorrect point deduction	|Medium |	Medium	|Medium	| Validate score calculations after hint usage|

### Risk Coverage

**Tested Risks Percent:** 83%  
**Untested Risks Percent:** 17%

*(Pie Chart Representation)*  
🟢 Tested Risks – 83%  
🔴 Untested Risks – 17%


## Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|---------|-----------|----------------|---------------|--------|-----------|
| TC-01 |Basic Gameplay	|Verify word scrambling and guessing	|Word scrambled, correct guess accepted|	PASS |Passed| -	|
| TC-02 |Score Calculation	|Test scoring without hints	|+10 points for correct guess|	PASS	|Passed	| -| 
| TC-03 |Hint System	|Verify hint cost and reduced points	|-2 points immediately, +5 for solve | PASS	|Passed	| R7 |
| TC-04 |Leaderboard	|Verify top-3 sorting logic|	Scores sorted descending	|PASS	|Passed| R4 |
|TC-05  |Bonus Round	|Test bonus triggering every 3 solves|	Score doubles after 3rd puzzle	|PASS	| R3 |
| TC-06 |Reset Game	|Verify complete state reset|	Score=0, progress cleared	|PASS	|Passed	| R1 |
| TC-07 |Negative Test	|Enter incorrect guess|	Error message displayed		| - | -|
| TC-08 |Usability	|Keyboard navigation	All functions accessible via keyboard |PARTIAL	|Failed	| Failed | R5 |


## Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|-------------|----------|---------|--------|-------------|
|001 |Scrambled word chatbox remains blank after reset. Disappears only when "new puzzle" is clicked | Medium | R1|open |https://github.com/PLP-Database-Design/wk-5-ngarama2025-1/issues/2#issue-3557771204|
|002 | Hint button can be clicked twice before score updates|low |R4|fixed |https://github.com/PLP-Database-Design/wk-5-ngarama2025-1/issues/3#issue-3557789878 |
|003 |Success message disappears too fast| low| R5| open| https://github.com/PLP-Database-Design/wk-5-ngarama2025-1/issues/4#issue-3557801540 |

## Metrics

- Test Case Pass Percent: 87.5% 

- Defect Density: 0.375 defects/test case 

- Risk Coverage Percent: 83%

- Regression Success Rate: 100% 
### Defect Summary

- TTotal Defects Logged: 3

- Critical/High: 0

- Medium: 1

- Low: 2

Fix Rate: 67%

#### Test Executor summary
All critical functionalities — Reset, leaderboard, and bonus round were executed successfully. The only issues found were minor UI/UX delays that do not affect core game logic.
Overall, the game performed well under manual test execution in Chrome, and evidence confirmed that all key features meet the design expectations.

## Test Control & Project Management

### Phases

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|-------------|---------------|----------|-------|
| Planning | Test Plan	| Comprehensive plan	|None |	Test Manager|
| Analysis |Risk Assessment | 7 risks identified	| +1 risk	|Risk Analyst|
|Design	| Test Cases	| 8 test cases |	None	|Test Executor |
| Execution |	Test Results |	87.5% pass rate	| -12.5% |	Test Executor
|Reporting	| Defect Log	|3 issues logged |	None	| All |

**Progress Tracking Method:**  Daily standups, GitHub Issues tracking
 
**Change Control Notes:** No scope changes required during testing cycle

## Lessons Learned

- Most Defect Prone Feature:  Leaderboard functionality
- Risk Analysis Impact: 
- Team Communication Effectiveness: Good coordination through daily syncs
- Improvements for Next Cycle:
  - Include more negative test scenarios

  - Enhance accessibility testing coverage
 
  - Implement automated regression tests

## Attachments

- Github issues

## Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Prifton Mliwa | Test Manager | PM | 28-10-2025 |
| Peter Adebisi | Risk Analyst | PA |28-10-2025 |
| Lena Wahu | Test Executor | LW |28-10-2025 |

## Overall Summary
**Statement:** The Word Puzzle Game Plus has been thoroughly tested with 87.5% test case pass rate. Three defects were identified and logged. The risk-based testing approach effectively prioritized testing efforts and uncovered critical issues early in the phases.
**Statement:** 

**Test Status:** ☑ Completed / ☐ In Progress / ☐ Deferred
