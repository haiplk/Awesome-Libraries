# Clean Code Summary

## Introduction

"Clean Code" by Robert C. Martin (Uncle Bob) is a guide to writing clean, maintainable, and understandable code. It provides principles and practices that can help developers produce high-quality software.

## Key Principles

### 1. Meaningful Names

Choose clear and descriptive names for variables, functions, and classes. Names should reveal intentions and avoid ambiguity.


```csharp
// Bad
int d; // elapsed time in days

// Good
int elapsedTimeInDays;
```

### 2. Functions

Keep functions short and focused, aiming for clarity and readability. Each function should do one thing and do it well.

### 3. Comments

Write code that is self-explanatory, minimizing the use of comments. Favor expressive code over explanatory comments.

### 4. Formatting

Maintain consistent formatting to enhance readability and maintain a professional appearance. Follow a consistent style guide.

### 5. Objects and Data Structures

Encapsulate data and behavior within objects. Avoid exposing internal details unnecessarily.

### 6. Error Handling

Use exceptions rather than returning error codes. Handle errors at the appropriate level of abstraction.

### 7. Boundaries

Clearly define interfaces with external systems. Wrap third-party APIs to protect the internal codebase.

### 8. Unit Tests

Write comprehensive unit tests to verify the correctness of individual units of code. Tests should be readable, maintainable, and automated.

### 9. Classes

Keep classes small and focused, adhering to the Single Responsibility Principle (SRP). Each class should have only one reason to change.

### 10. Systems

Design modular and decoupled systems. Favor composition over inheritance and strive for loose coupling.
