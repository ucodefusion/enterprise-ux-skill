# Review checklist and acceptance criteria

## Before implementation
Identify user role, task, frequency, data volume, risks, viewport and existing patterns. Map current and proposed workflow and justify component/container choice.

## Design review
Check navigation scope, action placement, visible frequent options, settings scope, density, responsive layout and all states. Verify accessibility and recovery paths.

## Implementation review
Reuse design system; preserve state; enforce permissions and server validation; prevent duplicate submission; test keyboard, focus and errors; avoid unrelated changes.

## Acceptance tests
Given a filtered list, when a record is edited and closed, filters and position remain. Given a small frequent option set, selection is direct if space permits. Given failed save, input remains and retry is possible. Given keyboard-only navigation, every task is operable.

## Evidence and reporting
Report current vs proposed steps, files changed, component choices, test results, unresolved risks and exceptions. Mark untested items explicitly; do not claim validation not performed.
