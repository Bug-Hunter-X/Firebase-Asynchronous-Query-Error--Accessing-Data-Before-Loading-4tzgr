# Firebase Asynchronous Query Error
This repository demonstrates a common yet subtle error when working with Firebase Realtime Database queries. The issue arises from attempting to access data before the asynchronous query completes, potentially leading to undefined values and application crashes.

## Problem
The `on('value', ...)` method is asynchronous.  If you try to access data within the callback before the data is fully retrieved, it will result in an error because `snapshot.val()` might return `undefined` or `null`.

## Solution
The solution involves proper error handling and ensuring the data is available before accessing it.  This can be achieved through checks within the callback to verify if the data exists before processing it.

## Usage
1. Clone this repository.
2. Install the Firebase SDK: `npm install firebase`
3. Configure your Firebase project.
4. Run the `bug.js` file to see the error. 
5. Run the `bugSolution.js` file to see the corrected version.