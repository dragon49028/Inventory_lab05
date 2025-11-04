# Inventory_lab05
| Issue || Tool || Line(s) || Description || Fix Applied |
|--------||-------||----------||-------------||-------------|
| 'logging' imported but unused || Flake8 || 2 || Unused module imported || Removed the logging import |
| E302 expected 2 blank lines || Flake8 || 8, 14, 22, 25, 31, 36, 41, 48 || PEP8 requires 2 blank lines before functions || Added extra blank lines before function definitions |
| E305 expected 2 blank lines after function definition || Flake8 || 61 || Not enough blank lines before main block || Added 2 blank lines before if __name__ == "__main__": |
| E722 do not use bare 'except' || Flake8 || 19 || Bare exception used without specific type || Replaced with except KeyError: |
| W292 no newline at end of file || Flake8 || 61 || Missing newline at file end || Added newline at EOF |
| Mutable default argument logs=[] || Pylint || add_item() || Shared mutable list across calls || Changed to logs=None and initialized inside function |
| Insecure use of eval() || Bandit || Bottom of file || Dangerous function allowing code injection || Removed eval() entirely |
| File not opened safely || Manual || load_data() & save_data() || Files opened without context manager || Used with open() for safe file handling |
| No input validation || Manual || add_item() || Function accepted invalid types || Added type checking for both item and qty |
