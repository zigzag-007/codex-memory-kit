# Scripts Folder Rules: Batch and PowerShell

These rules apply to any `.bat`, `.cmd`, or `.ps1` file in this folder and its subfolders. This file only loads when Codex is working on files in this folder, because it sits closest to them.

## Response Method

Follow the UARSC method for any task in this folder: Understand, Analyze, Reason, Synthesize, Conclude.

## Rules

1. **Exit pattern**: `exit /b` inside a nested function returns to the caller, not the script's starting point. Pattern to use: the nested function sets a flag, calls `exit /b`, then the parent checks the flag and exits itself if needed.

2. **Error handling**: Never rely on `%errorlevel%`. Use `&&` and `||` for simple chains. To verify a command worked, check the real outcome, such as whether a file exists or a registry value is set, not the command's return code.

3. **Execution**: Never run commands directly on the user's real PC. Assume a virtual machine environment unless told otherwise.

4. **Output format**: Use the pattern `(file/folder)`, `[Successful/Failed]`, `[Details]`. Leave a blank line between phases. List successes before failures.

5. **Code quality**: Write production ready code with test cases, expected outputs, and edge cases covered. Check brackets and correctness twice.

6. **Compatibility**: Support Windows Vista through Windows 11. PowerShell version 2 or higher only. Write PowerShell as one line commands when it is embedded inside a batch file.

7. **Batch comments, which symbol to use**: Use `::` outside of parentheses blocks. Use `REM` inside `if`, `for`, or `&&()` blocks, since `::` gets misread as a drive letter inside those blocks.

8. **Batch comments, length**: Single line comments should be at least 60 characters. Deeper explanation comments should be 60 to 123 characters per line, and wrap to more lines if needed. Write them in a simple, beginner friendly way that shows understanding.

9. **Batch color functions**: Never use `()` inside `:color` text strings. Use `[]` instead. For example, write `"3 task[s]"`, not `"3 task(s)"`.

10. **FOR /F redirection**: Escape redirection inside command strings used in a FOR /F loop, using `2^>nul` or `%nul6%`. Outside of a FOR /F loop, use the normal `2>nul` or `%nul2%`.

11. **Registry verification**: After `reg add`, verify the result with `reg query` and check for the value. Do not trust the write command's return code alone. Apply the same idea to files and installers, check the real result.

12. **Code condensation**: Avoid setting redundant variables more than once. Sequential environment variable sets can be chained with `&&` only if there is no conditional branching, it stays easy to read, and there are no more than three variables in the chain. Keep logically separate steps on separate lines.

13. **Nested conditions**: When only one outcome should ever be true, use a nested `if / else if / else` structure, not several separate `if` blocks. Make sure exactly one branch runs. Avoid overlapping or duplicate conditions.
