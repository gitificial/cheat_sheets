## gdb cheat sheet

| **Command**                         | **Description**                                      |
|-------------------------------------|------------------------------------------------------|
| `run [args]`                        | Starts the program with optional arguments           |
| `quit` / `exit`                     | Exits the debugger                                   |
| `break <function_name>`             | Sets a breakpoint at the function                    |
| `break <file_name>:<line_number>`   | Sets a breakpoint at the specific line number        |
| `delete <breakpoint_number>`        | Deletes a specified breakpoint                       |
| `continue`                          | Continues execution until the next breakpoint        |
| `step`                              | Steps through the program, stepping into functions  |
| `next`                              | Steps over a function call                          |
| `finish`                            | Steps out of the current function                   |
| `backtrace`                         | Displays the call stack                             |
| `info registers`                    | Displays the contents of CPU registers              |
| `print <variable_name>`             | Prints the value of a variable                      |
| `x/<format> <address>`              | Examines memory at the specified address            |
| `list`                              | Displays the source code around the current line     |
| `watch <variable_name>`             | Sets a watchpoint to break when a variable changes   |
| `attach <pid>`                      | Attaches GDB to a running process                   |
| `info threads`                      | Lists all threads in the program                    |