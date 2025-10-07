# Component Creation Template

## Purpose
Generate UI components with proper structure, props, state management, and styling.

## Template

```
I need you to create a [framework] component with the following specifications:

**Component Name**: [ComponentName]
**Framework**: [React/Vue/Angular/Svelte]
**Component Type**: [Functional/Class/etc.]
**Purpose**: [clear description of what the component does]

**Props/Inputs**:
- [prop1]: [type] - [description] (required/optional)
- [prop2]: [type] - [description] (required/optional)

**State/Data**:
- [state1]: [type] - [description]
- [state2]: [type] - [description]

**Events/Callbacks**:
- [event1]: [description] - emitted when [condition]
- [event2]: [description] - emitted when [condition]

**UI Requirements**:
- [requirement 1]
- [requirement 2]
- Responsive design
- Accessibility (ARIA labels, keyboard navigation)

**Styling**:
- [CSS/SCSS/Styled-components/Tailwind/etc.]
- [specific style requirements]

**Behavior**:
- [behavior 1]
- [behavior 2]

**Dependencies**: [list any required libraries]
```

## Example

```
I need you to create a React component with the following specifications:

**Component Name**: SearchBar
**Framework**: React (with TypeScript)
**Component Type**: Functional component with hooks
**Purpose**: A reusable search bar with autocomplete suggestions

**Props/Inputs**:
- placeholder: string - Placeholder text (optional, default: "Search...")
- onSearch: (query: string) => void - Callback when search is submitted (required)
- suggestions: string[] - Array of autocomplete suggestions (optional)
- debounceMs: number - Debounce delay in ms (optional, default: 300)

**State/Data**:
- query: string - Current search input value
- showSuggestions: boolean - Whether to show suggestion dropdown
- selectedIndex: number - Currently selected suggestion index

**Events/Callbacks**:
- onSearch: Called when user submits search (Enter key or button click)
- onChange: Internal handler for input changes

**UI Requirements**:
- Input field with search icon
- Clear button (X) when input has text
- Dropdown list of suggestions below input
- Highlight selected suggestion
- Show loading spinner during debounce
- Responsive design for mobile and desktop
- Accessibility (ARIA labels, keyboard navigation with arrow keys)

**Styling**:
- Use CSS Modules
- Clean, modern design
- Smooth transitions for dropdown
- Focus states for accessibility
- Mobile-friendly touch targets

**Behavior**:
- Debounce input changes before showing suggestions
- Filter suggestions based on input
- Arrow keys to navigate suggestions
- Enter key to select suggestion or submit search
- Escape key to close suggestions
- Click outside to close suggestions
- Auto-focus on mount (optional prop)

**Dependencies**: React, TypeScript
```

## Tips

1. **Specify the framework and version** for accurate syntax
2. **Define props clearly** with types and whether they're required
3. **Describe behavior in detail** including interactions and animations
4. **Include accessibility requirements** (ARIA, keyboard navigation)
5. **Specify styling approach** (CSS-in-JS, modules, utility classes)
6. **Request responsive design** if needed for multiple screen sizes
7. **Mention state management** if using Redux, Context, etc.
8. **Include TypeScript types** if using TypeScript
