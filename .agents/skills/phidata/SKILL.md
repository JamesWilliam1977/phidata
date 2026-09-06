```markdown
# phidata Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `phidata` Python codebase. You'll learn how to structure files, write imports and exports, follow commit conventions, and implement and test new features in a consistent manner. This guide is ideal for contributors aiming for high-quality, maintainable code in the `phidata` project.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `data_loader.py`, `user_profile_manager.py`

### Import Style
- Use **relative imports** within the package.
  - Example:
    ```python
    from .utils import parse_config
    from ..models import User
    ```

### Export Style
- Use **named exports**; explicitly specify what is exported from a module.
  - Example:
    ```python
    __all__ = ["MyClass", "my_function"]
    ```

### Commit Patterns
- Commit messages are mixed but often use prefixes like `fix` or `cookbook`.
  - Example: `fix: handle edge case in parser`
  - Example: `cookbook: add new example for API usage`

## Workflows

### Adding a New Module
**Trigger:** When you need to add a new feature or component.
**Command:** `/add-module`

1. Create a new Python file using snake_case (e.g., `new_feature.py`).
2. Implement your functionality.
3. Use relative imports to access shared code.
4. Add named exports via `__all__`.
5. Write a corresponding test file (see Testing Patterns).
6. Commit your changes with a descriptive message, using a prefix if appropriate.

### Fixing a Bug
**Trigger:** When you identify and resolve a bug.
**Command:** `/fix-bug`

1. Locate the problematic code.
2. Apply the fix, following coding conventions.
3. Add or update tests to cover the bug.
4. Commit with a message starting with `fix:`, e.g., `fix: resolve index error in data loader`.

### Writing a Cookbook Example
**Trigger:** When you want to document usage or provide an example.
**Command:** `/add-cookbook`

1. Create or update a file prefixed with `cookbook_` or in the cookbook directory.
2. Write clear, concise example code.
3. Use relative imports as needed.
4. Commit with a message starting with `cookbook:`, e.g., `cookbook: add example for config parsing`.

## Testing Patterns

- Test files follow the pattern `*.test.*` (e.g., `data_loader.test.py`).
- The specific testing framework is not enforced; use standard Python testing practices.
- Place tests close to the modules they test or in a dedicated tests directory.
- Example test file:
  ```python
  # data_loader.test.py
  from .data_loader import load_data

  def test_load_data_valid():
      assert load_data("input.csv") is not None
  ```

## Commands
| Command         | Purpose                                      |
|-----------------|----------------------------------------------|
| /add-module     | Scaffold and implement a new module          |
| /fix-bug        | Apply and commit a bug fix                   |
| /add-cookbook   | Add or update a cookbook/example file        |
```
