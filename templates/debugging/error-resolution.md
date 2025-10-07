# Error Resolution Template

## Purpose
Resolve specific errors and exceptions by providing full context and error details.

## Template

```
I'm encountering an error and need help resolving it:

**Error Message**:
```
[paste the complete error message]
```

**Stack Trace** (if applicable):
```
[paste full stack trace]
```

**Programming Language**: [language]
**Framework/Libraries**: [relevant frameworks]

**Context**:
[What were you trying to do when the error occurred?]

**Code That Triggers the Error**:
```[language]
[paste the code that causes the error]
```

**Related Code** (if applicable):
```[language]
[paste any related code sections]
```

**Environment**:
- OS: [operating system]
- Language Version: [version]
- Framework Version: [version]
- [other relevant tools/versions]

**When Does It Occur**:
[Always / Sometimes / Under specific conditions]

**Conditions**:
[Specific conditions that trigger the error]

**What I've Already Tried**:
- [attempt 1]
- [attempt 2]

Please help me:
1. Understand what this error means
2. Identify the root cause
3. Provide a working solution
4. Explain how to prevent this in the future
```

## Example

```
I'm encountering an error and need help resolving it:

**Error Message**:
```
TypeError: Cannot read property 'map' of undefined
```

**Stack Trace**:
```
TypeError: Cannot read property 'map' of undefined
    at UserList (UserList.js:15)
    at renderWithHooks (react-dom.development.js:14985)
    at mountIndeterminateComponent (react-dom.development.js:17811)
    at beginWork (react-dom.development.js:19049)
    at HTMLUnknownElement.callCallback (react-dom.development.js:3945)
```

**Programming Language**: JavaScript
**Framework/Libraries**: React 18.2.0, Redux 4.2.0

**Context**:
I'm building a user management interface. The error occurs when the UserList component tries to render. The data comes from a Redux store that's populated by an API call.

**Code That Triggers the Error**:
```javascript
// UserList.js
import React from 'react';
import { useSelector } from 'react-redux';

function UserList() {
  const users = useSelector(state => state.users.data);
  
  return (
    <div>
      <h2>Users</h2>
      <ul>
        {users.map(user => (
          <li key={user.id}>{user.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default UserList;
```

**Related Code**:
```javascript
// usersSlice.js
import { createSlice, createAsyncThunk } from '@reduxjs/toolkit';

export const fetchUsers = createAsyncThunk(
  'users/fetchUsers',
  async () => {
    const response = await fetch('/api/users');
    return response.json();
  }
);

const usersSlice = createSlice({
  name: 'users',
  initialState: {
    data: undefined,
    loading: false,
    error: null
  },
  extraReducers: (builder) => {
    builder
      .addCase(fetchUsers.pending, (state) => {
        state.loading = true;
      })
      .addCase(fetchUsers.fulfilled, (state, action) => {
        state.loading = false;
        state.data = action.payload;
      });
  }
});
```

**Environment**:
- OS: Windows 11
- Node: 18.16.0
- React: 18.2.0
- Redux Toolkit: 1.9.5

**When Does It Occur**:
Always on initial page load, before the API call completes

**Conditions**:
The error happens when the component renders before the Redux store is populated with user data.

**What I've Already Tried**:
- Adding console.log to check users value (it's undefined on first render)
- Wrapping the map in a conditional (users && users.map(...)) which works but feels wrong

Please help me:
1. Understand why users is undefined initially
2. Identify the proper way to handle this in React/Redux
3. Provide best practice solution for async data loading
4. Explain how to handle loading states properly
```

## Tips

1. **Include the complete error message** word-for-word
2. **Provide the full stack trace** for better diagnosis
3. **Show the exact code** that triggers the error (not paraphrased)
4. **Include related code** that sets up the context
5. **Specify versions** as errors can be version-specific
6. **Describe when it occurs** (always, sometimes, under what conditions)
7. **Mention attempted solutions** to avoid repetition
8. **Use proper formatting** for error messages and stack traces
