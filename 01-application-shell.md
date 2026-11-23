# Application shell and screen architecture

## Global header
Keep logo, workspace switcher, global search, quick create, help, notifications and profile accessible. Avoid duplicating module navigation.

## Primary sidebar / top menu
Use a collapsible sidebar for many modules; use a top menu for a small flat set. Keep active location visible; avoid deep nesting.

## Page header and breadcrumbs
Place breadcrumbs above the title; title and record identity on the left, primary page action on the right. Breadcrumbs link to ancestors, not arbitrary history.

## Footer and status bar
Use a sticky contextual footer for long forms with Cancel and Save; keep version, connectivity and legal links in a separate compact status area only when useful.

## Right contextual panel
Place notes, related records, history and quick actions in a collapsible panel. Preserve main content width and focus.

## Layout example
Global header > primary navigation + content (breadcrumb, title/actions, tabs, toolbar, content) + optional contextual panel > optional action footer.

## Mandatory layout contract
Use semantic header, navigation, main and footer landmarks. A desktop shell should have one global header, one primary navigation region, and one main content region. Render a contextual right panel only when it supports the current task. Do not introduce another full-width header for each nested component.

| Region | Default placement | Contents | Exclude |
|---|---|---|---|
| Global header | Top, persistent when useful | Workspace switch, global search, notifications, account, global create | Record-specific save/delete |
| Primary navigation | Left for many modules; top for a small flat product | Module routes, active state, pinned items | Form fields, row actions |
| Sidebar bottom | Below module navigation | Organisation settings, help, collapse | Frequently used core modules |
| Breadcrumb | Immediately above page title | Linked ancestors, current page as text | Browser history, duplicated tabs |
| Page header | Title left, actions right | Identity, status, primary action, secondary actions | Global profile, unrelated filters |
| Record tabs | Below page header | Related sections of same record | Unrelated modules |
| Table toolbar | Directly above results | Search, filter, sort, view, export, selection actions | Global settings |
| Contextual panel | Right of main region | Notes, related records, history | Essential information available nowhere else |
| Action footer | Bottom of editing region | Save, Cancel, Next, Back, submission status | Copyright or unrelated navigation |
| Application footer | End of document or small status area | Version, legal/support links if useful | Primary task actions |

## Screen blueprints
```text
GLOBAL: Brand | Workspace | Search / Cmd+K | Quick create | Alerts | Profile
NAVIGATION        MAIN
Modules           Breadcrumb
                  Title + record status                Primary action | More
                  Record tabs
                  Search | Filters | Saved view       Export | Columns
                  Data / form / workspace             Optional related panel
                  Contextual sticky footer            Cancel | Save
Settings / Help
```
List screens: page title and Create above toolbar; bulk actions replace or augment toolbar only when selection exists. Detail screens: record identity, status and common actions above tabs; show a concise summary before deep sections. Edit screens: grouped fields, validation near fields, action footer if long. Dashboards: actionable exceptions before decorative metrics. Settings: scope-specific navigation and section anchors. Wizards: step indicator, current step, Back and Next; do not demand completion of irrelevant steps.

## Layout sizing and behaviour
Use existing tokens first; example starting values only: desktop sidebar 224–256px, collapsed 56–72px, header 48–64px, spacing increments 4/8/12/16/24/32px. Set main flex child min-width: 0 and let tables scroll inside their own container when necessary. Avoid fixed widths that break zoom or translation. Prefer CSS grid/flex and sticky positioning over absolute coordinates. Sticky regions must not obscure focused content or consume excessive viewport height. On narrow screens collapse primary navigation and convert optional side panels into accessible sheets or full-page routes. Do not make the entire document horizontally scrollable just because a table is wide.

## Acceptance tests
- From every module, open another authorised module without visiting Dashboard first.
- From a deep record, use a breadcrumb to return to its parent; preserve list context when a valid prior list state exists.
- At narrow viewport and 200% zoom, primary action and navigation remain reachable; focused controls are not obscured.
- Long form: Save/Cancel remain available where appropriate without covering the last field; no duplicate competing primary buttons.
- If contextual panel closes, focus returns to its trigger and main data is preserved.
