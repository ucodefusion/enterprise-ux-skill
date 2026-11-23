# Interaction cost and workflow optimisation

## Core principles
Apply Fitts’s law (reachable targets), Hick’s law (manageable choices), recognition over recall, visual hierarchy, progressive disclosure, direct manipulation and spatial consistency.

## Direct actions
Use inline editing, contextual quick create, clickable record IDs, expandable rows and quick previews. Use drawers rather than page changes for short edits.

## Repeated work
Support bulk actions, duplicate/clone, templates, saved searches, recently used actions and keyboard shortcuts. Show selected count and scope for bulk changes.

## Smart defaults
Prefill known values, remember non-sensitive preferences, suggest next actions and auto-apply simple filters when performance permits.

## Recovery and safeguards
Use undo for safe reversible operations; confirmations for irreversible or high-impact actions. Never remove security, permission or review steps just to reduce clicks.

## Workflow example
Before: list > record > settings > edit > save > back. After: locate row > change status inline > feedback/undo; preserve list state. Measure actual completion time and errors, not just clicks.

## Workflow optimisation procedure
List top tasks by role and frequency; establish baseline pointer actions, keystrokes, screen transitions, scrolling, waiting and errors. Identify unnecessary opening, navigation, confirmation, duplicate data entry or re-search. Remove redundant steps before adding automation. Preserve necessary review for irreversible, financial, privacy-sensitive or permission-changing operations. Validate improvement with representative tasks; do not invent metrics.

| Pattern | Use | Implementation requirements |
|---|---|---|
| Inline edit | One or few low-risk fields | Explicit edit affordance, validation, pending/saved/error, rollback |
| Drawer | Short edit or preview from list | Preserve list state, labelled title, close/return focus, draft guard |
| Bulk action | Repeated operation over records | Selection count, scope, permissions, partial failure report |
| Quick create | Related record required mid-task | Prepopulate parent ID, return created record, preserve form |
| Duplicate/template | Repetitive record creation | Reset identifiers, audit fields and sensitive attributes; review copied data |
| Command palette | Expert cross-module navigation | Search authorised commands, keyboard shortcuts, labelled discoverable entry |
| Saved views | Repeated filters | Name, owner/scope, explicit save/reset, valid filters on reopening |
| Auto-save | Reversible low-risk edits | Debounce, visible save status, retry, conflict handling |
| Undo | Reversible action | Actual reversal mechanism, clear time window if any |
| Previous/Next | Sequential review | Respect active list order and filters, guard drafts |
| Split button | Common action plus variants | Primary label executes common action; separate menu opens alternatives |

## Bulk operation contract
Checkboxes identify individual rows. Select all visible rows and select all matching results must be distinguishable. Show selected count and filter scope before applying. Server revalidates permissions and eligible state for each record. Use idempotency or duplicate protection when needed. Show success/failure counts and retry failed items without repeating successful ones. Clear selection only when appropriate; do not silently include hidden records.

## Example task analysis
Change five customer statuses: old workflow opens five detail pages, edits and saves each, and returns to list. Proposed workflow selects five rows, chooses Change status, reviews scope if risk warrants, applies once and sees per-record outcomes. Count actual actions in both versions; verify filtered state and selection after partial failure. Never bypass required approval to save clicks.

## Agent guardrails
Do not add hover-only shortcuts, surprise auto-navigation, hidden gesture-only actions or unnecessary confirmations. Avoid moving familiar actions without evidence. Use predictable keyboard shortcuts that do not override text entry or browser controls. Prefer one clear primary action per task region, not necessarily per entire complex workspace.
