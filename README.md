# Chat Application with RTK Query

### Project setup

#### Server setup and Requirement Analysis

#### Requirement Analysis

- 1. User can register. After registering, user will be automatically logged in, we will store login info to localStorage (for login persistance) and redirected to inbox page
- 2. User can login and after login we will save the login information in localStorage (for login persistance) and redirect user to inbox
- 3. Load sidebar messages from conversation API and implement load more feature.
- 4. Load specific conversation messages when use clicks on it and implement load more feature.
- 5. ###### When user sends message,
- a) If conversation id is present, update conversation table and also inserts into messages table.
- b) If conversation id is missing, get conversation id using filter
- If conversation id exists, then update that conversation and add to messages table
- If conversation id is missing, insert that conversation and add to messages table.
- 6. Sidebar conversation list scroll - sort by latest first and when user loads more, bring previous '10 conversation sorted by latest first' and pushed into the conversation array.
- 7. Messages list scroll - bring '10 latest messages per request sorted by oldest first'. When user loads more, 'bring previous 10 messages sorted again by oldest first' and unshift into the array.

#### Required APIs

- 1. Register
- 2. Login
- 3. Get list fo users other than requesting user
- 4. Update conversation
- 5. Insert conversation
- 6. Find conversation
- 7. List conversation
- 8. List messages by conversation id
- 9. Send message (insert messages into messages table)

### Create API Slice

#### Configure the store - Code Splitting

- Create common apiSlice and it takes all extra api.
- For big project you need to create extra place to put features wise api and slice.
- You can easily use it by this keyword like injectEndpoints and it's help our code maintainable.
- If we don't want to show redux devtools in production level then we can use it in store section

```
devTools: process.env.NODE_ENV !== 'production',
```

### Auth API and Slice

#### Creating API and Slice for Authentication
