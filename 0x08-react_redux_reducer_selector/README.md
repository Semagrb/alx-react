# 0x08. React Redux reducer+selector

## Introduction

Welcome to the **0x08. React Redux reducer+selector** project. This project focuses on implementing Redux reducers and selectors in a React application. The goal is to enhance state management by applying best practices and utilizing libraries such as Immutable.js and Normalizr.

## Table of Contents

- [Introduction](#introduction)
- [Resources](#resources)
- [Learning Objectives](#learning-objectives)
- [Project Structure](#project-structure)
- [Tasks](#tasks)
  - [0. Write a basic reducer](#0-write-a-basic-reducer)
  - [1. Use Immutable for the UI Reducer](#1-use-immutable-for-the-ui-reducer)
  - [2. Create a reducer for Courses](#2-create-a-reducer-for-courses)
  - [3. Create the reducer for notifications](#3-create-the-reducer-for-notifications)
  - [4. Normalizr & Immutable](#4-normalizr--immutable)
  - [5. Selectors](#5-selectors)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Resources

To help you understand and implement Redux reducers and selectors, the following resources are recommended:

- [Reducers](https://redux.js.org/tutorials/fundamentals/part-3-state-actions-reducers)
- [Selectors](https://redux.js.org/usage/deriving-data-selectors)
- [Writing tests](https://redux.js.org/usage/writing-tests)
- [Immutable Map documentation](https://immutable-js.github.io/immutable-js/docs/#/Map)
- [Normalizr](https://github.com/paularmstrong/normalizr)
- [Normalizing State Shape](https://redux.js.org/usage/structuring-reducers/normalizing-state-shape)

## Learning Objectives

At the end of this project, you should be able to explain to anyone, without the help of Google:

- The purpose of a reducer and the role it plays within your application.
- Why a reducer should stay as pure as possible.
- Why mutations should not happen within a reducer.
- The use of Immutable within the reducer.
- The use of Normalizr within the app.
- Selectors: what they are and when to use them.

## Project Structure

The project is organized as follows:

```
0x08-react-redux-reducer-selector/
├── src/
│   ├── actions/
│   ├── components/
│   ├── reducers/
│   ├── schema/
│   ├── selectors/
│   ├── store/
│   ├── tests/
│   ├── App.js
│   ├── index.js
│   └── ...
├── .gitignore
├── package.json
├── README.md
└── ...
```

## Tasks

### 0. Write a basic reducer

**Directory:** `task_0/dashboard/src/reducers`

- **File:** `uiReducer.js`
- **Initial State:**
  - `isNotificationDrawerVisible: false`
  - `isUserLoggedIn: false`
  - `user: {}`

**Actions:**
- `DISPLAY_NOTIFICATION_DRAWER` sets `isNotificationDrawerVisible` to `true`.
- `HIDE_NOTIFICATION_DRAWER` sets `isNotificationDrawerVisible` to `false`.
- `LOGIN_SUCCESS` sets `isUserLoggedIn` to `true`.
- `LOGIN_FAILURE` sets `isUserLoggedIn` to `false`.
- `LOGOUT` sets `isUserLoggedIn` to `false`.

**Tests:**
- Test the initial state.
- Test state with `SELECT_COURSE` action.
- Test state change with `DISPLAY_NOTIFICATION_DRAWER` action.

### 1. Use Immutable for the UI Reducer

**Directory:** `task_1/dashboard/src/reducers`

- **File:** `uiReducer.js`
- Use `Immutable.Map` for the initial state.
- Update reducer to use `set` from `Immutable.Map`.

**Tests:**
- Ensure tests account for `Immutable.js` changes.

### 2. Create a reducer for Courses

**Directory:** `task_2/dashboard/src/reducers`

- **File:** `courseReducer.js`
- **Initial State:** `[]`

**Actions:**
- `FETCH_COURSE_SUCCESS` updates state with fetched courses.
- `SELECT_COURSE` updates `isSelected` to `true` for the selected course.
- `UNSELECT_COURSE` updates `isSelected` to `false` for the unselected course.

**Tests:**
- Test the default state.
- Test `FETCH_COURSE_SUCCESS` action.
- Test `SELECT_COURSE` action.
- Test `UNSELECT_COURSE` action.

### 3. Create the reducer for notifications

**Directory:** `task_3/dashboard/src/reducers`

- **File:** `notificationReducer.js`
- **Initial State:**
  - `notifications: []`
  - `filter: "DEFAULT"`

**Actions:**
- `FETCH_NOTIFICATIONS_SUCCESS` updates state with fetched notifications.
- `MARK_AS_READ` updates `isRead` to `true` for the specified notification.
- `SET_TYPE_FILTER` updates the `filter` state.

**Tests:**
- Test the default state.
- Test `FETCH_NOTIFICATIONS_SUCCESS` action.
- Test `MARK_AS_READ` action.
- Test `SET_TYPE_FILTER` action.

### 4. Normalizr & Immutable

**Directory:** `task_4/dashboard/src/schema`

- **Files:**
  - `courses.js` for course schema and normalizer.
  - `notifications.js` for notification schema and normalizer.

**Reducers:**
- Update `courseReducer.js` and `notificationReducer.js` to use `Immutable.js` and `Normalizr`.

**Tests:**
- Update tests to account for changes in reducers.

### 5. Selectors

**Directory:** `task_5/dashboard/src/selectors`

- **File:** `notificationSelector.js`
- Create selectors:
  - `filterTypeSelected` returns the current filter.
  - `getNotifications` returns the list of notifications.
  - `getUnreadNotifications` returns the list of unread notifications.

**Tests:**
- Test each selector.

## Getting Started

To get started with this project, follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/0x08-react-redux-reducer-selector.git
    cd 0x08-react-redux-reducer-selector
    ```

2. **Install dependencies:**

    ```bash
    npm install
    ```

3. **Run the application:**

    ```bash
    npm start
    ```

## Usage

To use the reducers and selectors in your project, follow these steps:

1. **Define your reducers:** Create reducer functions in the `src/reducers` directory.
2. **Create selectors:** Define selectors in the `src/selectors` directory to derive and access specific pieces of state.
3. **Update the store:** Combine the reducers and integrate them into your Redux store, which is defined in the `src/store` directory.
4. **Connect components:** Use `react-redux` to connect your React components to the Redux store and access state and actions.

## Testing

Testing is crucial to ensure the correctness of your reducers and selectors. To run tests, use the following command:

```bash
npm test
```

Tests are located in the `src/tests` directory. Follow the best practices for writing tests as outlined in the [Writing tests](https://redux.js.org/usage/writing-tests) documentation.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

For major changes, please open an issue first to discuss what you would like to change.
