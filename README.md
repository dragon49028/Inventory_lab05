# Inventory_lab05
| Issue                    | Tool   | Line(s)                       | Description                                        | Fix Applied                                             |
| ------------------------ | ------ | ----------------------------- | -------------------------------------------------- | ------------------------------------------------------- |
| `F401`                   | Flake8 | 2                             | `'logging' imported but unused`                    | Removed unused `logging` import                         |
| `E302`                   | Flake8 | 8, 14, 22, 25, 31, 36, 41, 48 | Expected 2 blank lines before function definitions | Added required blank lines                              |
| `E305`                   | Flake8 | 61                            | Expected 2 blank lines after function definition   | Added 2 blank lines before `if __name__ == "__main__":` |
| `E722`                   | Flake8 | 19                            | Bare `except:` used                                | Replaced with `except KeyError:`                        |
| `W292`                   | Flake8 | 61                            | No newline at end of file                          | Added newline at end of file                            |
| Mutable default argument | Pylint | `add_item()`                  | `logs=[]` reused between calls                     | Changed to `logs=None` and initialized inside function  |
| Insecure `eval()`        | Bandit | Bottom of file                | Use of eval() creates security vulnerability       | Removed `eval()`                                        |
| File handling            | Manual | `load_data()` & `save_data()` | File opened without context manager                | Used `with open(...)`                                   |
| Input validation         | Manual | `add_item()`                  | Invalid types accepted                             | Added type checks for `item` and `qty`                  |

#Answers
1.The easiest issues to fix were the PEP 8 formatting problems reported by Flake8, such as missing blank lines, unused imports, and missing newlines at the end of the file. These were straightforward corrections that involved simple adjustments to spacing and structure.

The hardest issues were the mutable default argument (logs=[]) and the bare except: block. These required a deeper understanding of Python’s runtime behavior. The mutable default argument could cause data to persist unexpectedly across function calls, and the bare except: made debugging difficult by catching all exceptions. Fixing these required refactoring the logic and understanding how exception types and default parameters work internally in Python.
2.Yes. Pylint flagged the use of the global variable stock_data as a potential issue, suggesting it reduces code modularity. However, in this specific inventory system, stock_data serves as a shared state across all operations (add, remove, save, load). Since the design intentionally uses a single in-memory dictionary to manage inventory, this was considered a false positive rather than a design flaw.
3.I would integrate static analysis tools into the workflow through a combination of local and CI automation:

Configure pre-commit hooks to automatically run Flake8 and Pylint before every commit, ensuring code quality and style compliance.

Integrate Bandit in a GitHub Actions CI pipeline, so that every pull request is automatically scanned for security vulnerabilities.

Regularly review reports to catch regressions early and maintain consistent code quality throughout development.

This approach ensures that no insecure or non-compliant code is merged into the main branch.
4.After applying the fixes, the code became much more structured, secure, and maintainable.

Readability improved due to proper spacing, naming conventions (snake_case), and consistent formatting.

Security was enhanced by removing the unsafe eval() function and adding specific exception handling (except KeyError).

Robustness improved because the program now validates input types, uses context managers for file handling, and avoids shared mutable defaults.
Overall, the code evolved from a functional script into a cleaner, production-ready version that adheres to professional Python standards.
