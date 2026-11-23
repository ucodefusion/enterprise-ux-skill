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
