# Unhandled JSON Decoding Exception in Dart's Future

This repository demonstrates a common error in Dart asynchronous programming:  unhandled exceptions during JSON decoding within a `Future`. The `bug.dart` file showcases the problematic code, while `bugSolution.dart` provides a corrected version with robust error handling.

## Problem

The original `fetchData` function lacks comprehensive error handling. If the API returns invalid JSON or encounters a network issue resulting in a non-200 status code, a runtime error occurs.  The solution ensures the program gracefully handles this situation.

## Solution

The solution in `bugSolution.dart` improves the error handling by:

1. **Checking the response status code:** Ensures that the response from the API is successful before attempting to decode the JSON.
2. **Using a `try-catch` block:**  Handles potential exceptions during JSON decoding using `jsonDecode()`.
3. **Providing informative error messages:** Includes helpful details in error messages to aid in debugging.
4. **Rethrowing the exception:** Allows higher-level functions to handle the error if necessary.

This approach prevents unexpected crashes and enables better control over error management in asynchronous operations.