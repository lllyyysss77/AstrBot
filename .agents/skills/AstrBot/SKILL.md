```markdown
# AstrBot Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the AstrBot Python codebase. It covers the repository's coding conventions, commit message patterns, file organization, and testing approaches. By following these patterns, contributors can maintain consistency and quality across the project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `messageHandler.py`, `userSessionManager.py`

### Import Style
- **Mixed imports** are used, combining both absolute and relative imports as needed.
  - Example:
    ```python
    import os
    from .utils import parseMessage
    ```

### Export Style
- Use **named exports** by defining specific functions, classes, or variables to be imported elsewhere.
  - Example:
    ```python
    # In userSessionManager.py
    class UserSessionManager:
        ...
    def getSession(user_id):
        ...
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `feat` prefix for new features.
- Keep commit messages concise (average ~68 characters).
  - Example:
    ```
    feat: add user session management to improve chat continuity
    ```

## Workflows

### Feature Development
**Trigger:** When adding a new feature to AstrBot  
**Command:** `/feature-dev`

1. Create a new branch for your feature.
2. Implement the feature using camelCase file naming and mixed import styles.
3. Write or update tests in files matching `*.test.*`.
4. Commit changes using the `feat` prefix and a concise message.
5. Open a pull request for review.

### Testing
**Trigger:** When verifying code correctness  
**Command:** `/run-tests`

1. Locate or create test files using the `*.test.*` pattern.
2. Write tests for new or modified code.
3. Run tests using the project's preferred method (framework unknown; refer to project documentation or use standard Python test runners).
4. Ensure all tests pass before merging changes.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `messageHandler.test.py`).
- The specific testing framework is not detected; use standard Python testing tools such as `unittest` or `pytest` if unsure.
- Example test file:
  ```python
  # messageHandler.test.py
  import unittest
  from messageHandler import handleMessage

  class TestMessageHandler(unittest.TestCase):
      def test_handle_message(self):
          result = handleMessage("hello")
          self.assertEqual(result, "Hi there!")

  if __name__ == '__main__':
      unittest.main()
  ```

## Commands
| Command         | Purpose                                    |
|-----------------|--------------------------------------------|
| /feature-dev    | Start the feature development workflow      |
| /run-tests      | Run all test files in the codebase          |
```