# Input and interaction component selection

## Binary choice
Use a switch for an immediate reversible setting; radio buttons for yes/no in a form. Do not use a dropdown for two obvious choices when space permits.

## Small option sets
Use segmented controls for frequent view/filter switching (often 2–5 short options); radio lists for mutually exclusive choices with labels or descriptions.

## Native select
Use for familiar compact choices when showing all options would clutter the form. Usually open then select; native mobile behaviour can be beneficial.

## Searchable select / Select2
Use a combobox for many options or when users know the name. For large datasets use debounced server search, pagination, keyboard navigation and clear no-results/error states.

## Multiple and visual choices
Use checkbox lists for small multi-select sets; searchable multi-select with removable chips for large sets; selectable cards for meaningful visual differences.

## Other controls
Use stepper for small increments, number input for exact values, slider for approximate range, date picker with presets, tree selector for hierarchy, and quick chips for common values plus custom input.

## Interaction container
Tooltip: supplementary text; popover: small action; modal: focused interrupting task; drawer: quick contextual editing; full page: complex task; bottom sheet: mobile contextual options. Never hide required information in hover-only UI.

## Decision matrix (counts are heuristics, not hard limits)
| Requirement | Prefer | Avoid / reason |
|---|---|---|
| Immediate binary preference | Switch with label and feedback | Yes/no dropdown hides both options |
| Binary form answer | Radio group or checkbox if meaning is unambiguous | Switch implying immediate persistence |
| 2–5 short frequent filter choices | Segmented control | Dropdown adds opening step |
| 2–7 mutually exclusive choices with descriptions | Radio list | Tiny buttons with truncated text |
| Small familiar set, constrained space | Native select | Custom combobox without need |
| Many choices or lookup by known name | Searchable combobox / Select2-style control | Huge native select |
| Thousands of remote records | Async autocomplete | Fetching entire database |
| Small multi-select | Checkbox list | Repeated single-select operations |
| Large multi-select | Searchable multi-select with removable tokens | Hiding selected items |
| Meaningfully visual plans | Selectable cards with radio semantics | Decorative cards with no accessible state |
| Hierarchical options | Tree selector or staged selection | Flat ambiguous labels |
| Common durations | Preset buttons + custom | Repeated manual date entry |
| Exact numbers | Numeric input with units and validation | Slider as sole precise input |
| Approximate range | Slider with accessible value and optional numeric input | Unlabelled drag-only control |
| Frequent record switching | Master-detail list | Repeated dropdown and navigation |
| More related actions | Split button or labelled menu | Putting primary action only inside menu |

## Native select versus Select2 versus visible options
Use semantic native select when it meets the task; Select2 is one implementation, not a required dependency. A native select usually requires opening then choosing by pointer; radio/segmented options allow direct selection; searchable combobox reduces scanning effort but adds typing. Compare realistic tasks rather than assuming fewer pointer clicks always wins.
Example: status All/Active/Archived above customer table should be visible segments, with URL state and immediate filtering. Country in a compact address form may use a native select or accessible combobox depending on list length. Customer selection among 50,000 records must use authorised server-side search with stable IDs and disambiguating secondary labels.
```html
<fieldset>
  <legend>Account type</legend>
  <label><input type="radio" name="type" value="individual"> Individual</label>
  <label><input type="radio" name="type" value="business"> Business</label>
</fieldset>
<label for="currency">Currency</label>
<select id="currency" name="currency">
  <option value="NZD">NZD</option><option value="AUD">AUD</option>
</select>
```

## Searchable combobox implementation contract
Reuse an accessible design-system combobox. Maintain separate query, selected ID, display label, results, loading and error state. Debounce remote requests (e.g. 200–350 ms after measurement); abort or ignore stale responses. Return bounded results with pagination and use server-side tenant/role checks. Show current selected value even if absent from current result page; never silently clear it. Render loading, no results, retry, disabled and clear states. Provide accessible name, expanded state, active option announcement and keyboard support (Arrow keys, Enter, Escape, Tab). Do not commit arbitrary text when an existing record is required. For creatable controls make Create explicit and permission-checked. Distinguish duplicate names using appropriate non-sensitive identifiers. Multi-select must support keyboard removal, selection summary and explicit clear-all.

## Interaction container decision tree
One simple change: inline control. Supplementary description: tooltip (never essential information). Small anchored action: popover. Quick edit needing context: drawer. Short blocking decision: modal. Complex, shareable or long task: full page. Mobile contextual choice: bottom sheet if accessible. Do not nest dialogs or put long forms in tiny popovers. Modal/drawer must have appropriate focus management, Escape handling, accessible title and unsaved-change protection; only trap focus when modal.

## Acceptance criteria
Document option count, frequency, selection semantics and reason for control. Test pointer, keyboard and touch. Test empty and duplicate options, slow network, stale response, clear/reset, disabled and permission changes. Verify exact selected ID persists across reload and errors. No colour-only state; no placeholder-only labels.
