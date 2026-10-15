---
name: xuexitong-course-completion
description: Complete a user's Xuexitong safety or other course by auditing task points, watching required videos to the platform's completion threshold, answering embedded checks and chapter quizzes, submitting them directly, and verifying the final task count. Use only for an explicitly requested Xuexitong course-completion task.
metadata:
  platform: Windows
  category: education
---

# Xuexitong Course Completion

Use the computer-use skill to operate the already logged-in Xuexitong desktop or browser window. The goal is an observable course-completion result, not merely opening pages or filling answers.

## Authorization and scope

- Apply this skill only when the user asks to complete or continue a Xuexitong course.
- The user's standing preference in this workflow is to submit Xuexitong course forms and quizzes directly without an extra confirmation. Do not ask again before routine quiz/form submission.
- Do not bypass login, CAPTCHA, phone verification, proctoring, access controls, or platform restrictions. Leave those steps to the user.
- Keep all actions inside the selected Xuexitong course. Do not send messages, change grades, or alter unrelated account settings.

## Workflow

1. Open the course outline and record the visible completion state.
2. Audit the entire outline, including 导论, every numbered chapter, 拓展/资源 items, 阅读, and 调查问卷. A green check means complete; an orange/yellow badge means one or more task points remain. Do not infer completion from a previously visited page.
3. For each incomplete item:
   - Open it and wait for the content to load. Skip items that already show a green check or an in-page `任务点已完成` state; do not replay completed videos or retake completed quizzes.
   - Play the required video. Respect the page's stated completion rule, usually at least 90% watched. Do not skip ahead unless the platform itself permits it and the task visibly becomes complete. Clicking Play is not evidence of completion; verify both the in-page task state and the outline badge/counter.
   - When an embedded 判断题 or other interaction pauses playback, read the visible statement/options, select the answer supported by the lesson content, submit it, verify the green success feedback, and continue playback.
   - Open 章节测验, complete all questions, submit directly, and verify the result page or 已完成 state. For multi-select questions, select every supported option and avoid unsupported extras.
   - Check for extra resource videos or reading tasks linked to the same chapter; these can be separate task points.
4. After each meaningful milestone, recheck the outline. If an item remains yellow, reopen it and identify the specific unfinished task instead of assuming the prior action persisted.
5. At the end, scroll the outline from top to bottom and verify every required item. Prefer the course-level counter such as 已完成任务点: N/N as final evidence. Only report completion when the counter is complete and no required outline item has a pending badge.
6. If the page becomes unavailable, playback stops, or an answer is genuinely ambiguous, preserve the current state, report the concrete blocker, and wait for user action rather than guessing.

## Computer-use operating loop

- Select exactly one returned 学习通 window, activate it, and take an accessibility observation before every action.
- Treat element indexes, coordinates, and screenshot IDs as valid only for the observation that produced them. After every click, scroll, navigation, or modal change, capture a fresh state before choosing the next action.
- Prefer the outline's current list item to navigate between lessons. When the outline is virtualized or labels are missing, use the current screenshot to click the visible row, then refresh accessibility state; never guess an index from an earlier page.
- For long videos, leave playback running and inspect about every five minutes. If the player reports a real duration, do not claim completion until the stated threshold and the green task state are both visible.
- If Computer Use reports that the user stopped control, including a physical `Esc`, stop all further UI input in that turn. Preserve the current page and report the interruption; resume only in a later turn.

## Monitoring and communication

- During long videos, inspect progress about every five minutes. Use low-frequency checks and keep commentary quiet while playback is healthy.
- Notify only on a meaningful milestone, completion, failure, or required user action. Do not emit repetitive status messages or screenshots unless requested.
- Before and during long runs, check available Codex usage when the usage tool is available. Never expose account IDs or other account identifiers.
- If usage is exhausted or temporarily restricted, stop mutating actions, wait for the usage window to refresh, then resume from the current page and re-audit the current item.
- When complete, stop or delete any temporary monitor/heartbeat created specifically for this run.

## Evidence to report

Report the final visible task counter, the chapters or item types completed, and any unresolved blocker. Distinguish verified platform state from inference. A screenshot may be shown when the user asks for one.

