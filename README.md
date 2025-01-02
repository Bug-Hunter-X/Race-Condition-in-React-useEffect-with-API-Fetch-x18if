# Race Condition in React useEffect with API Fetch

This repository demonstrates a potential race condition in a React component that uses the `useEffect` hook to fetch data from an API. The component handles loading and error states but may encounter issues if it unmounts before the fetch completes.

## Description
The `bug.js` file contains a React component that fetches data from an API endpoint.  The component uses the `useEffect` hook to make the API call. If the component unmounts before the fetch completes, the promise returned by `fetch` might continue to resolve. This can cause stale updates in a subsequent render or throw unexpected errors.  This is a common issue that needs to be handled carefully.

## Solution
The `bugSolution.js` file demonstrates a solution using the `AbortController` API to cancel the fetch request if the component unmounts. This effectively handles the potential race condition, preventing unexpected behavior. 

## How to run
1. Clone the repository.
2. Navigate to the directory.
3. Run `npm install` to install the necessary dependencies.
4. Run `npm start` to start the development server.