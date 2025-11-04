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

