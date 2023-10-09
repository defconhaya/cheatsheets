### Basics
- **Shebang**: `#!/bin/bash` at the beginning of your script to specify the shell interpreter.

- **Comments**: `#` is used for single-line comments.

### Variables
```bash
variable_name="value"
```

- **Read Input**: `read variable_name` to read user input.

### Conditional Statements
```bash
if [ condition ]; then
    # code to execute if condition is true
elif [ another_condition ]; then
    # code to execute if another_condition is true
else
    # code to execute if none of the conditions are true
fi
```

### Loops
#### For Loop
```bash
for item in list; do
    # code to execute for each item in the list
done
```

#### While Loop
```bash
while [ condition ]; do
    # code to execute while condition is true
done
```

### Functions
```bash
function_name() {
    # code to define the function
    return
}
```

- **Function Invocation**: `function_name` to call a function.

### String Manipulation
- **Concatenation**: `$string1$string2` or `${string1}${string2}`.

- **Length**: `${#string}` gives the length of a string.

- **Substring**: `${string:start_index:length}` to extract a substring.

- **Find and Replace**: `${string/pattern/replacement}` to replace the first occurrence of `pattern` with `replacement`.

- **Regular Expressions**: Use `grep`, `sed`, or `awk` for more complex string manipulation.

### Arrays
```bash
my_array=("item1" "item2" "item3")
```

- **Accessing Elements**: `${my_array[index]}` to access a specific element.

- **Length**: `${#my_array[@]}` gives the number of elements.

- **Loop Through Array**:
  ```bash
  for item in "${my_array[@]}"; do
      # code to process each element
  done
  ```

### Command Substitution
```bash
result=$(command)
```

- **Capture Command Output**: `$(command)` captures the output of `command`.

### File Operations
- **Check if File Exists**: `if [ -e "$file" ]; then ...`

- **Check if Directory Exists**: `if [ -d "$dir" ]; then ...`

- **Create Directory**: `mkdir dirname`

- **Read File Line by Line**:
  ```bash
  while IFS= read -r line; do
      # process each line
  done < "$file"
  ```

- **File Permissions**: `chmod` to change file permissions.

- **File Ownership**: `chown` to change file ownership.

### Exit Status
- `0` indicates success.
- Non-zero values indicate an error.

### Special Variables
- `$0` - Name of the script.
- `$1`, `$2`, ... - Command line arguments.
- `$#` - Number of command line arguments.
- `$?` - Exit status of the last command.

### Redirection
- `command > file` - Redirect standard output to a file.
- `command 2> file` - Redirect standard error to a file.
- `command >> file` - Append standard output to a file.
- `command 2>> file` - Append standard error to a file.
- `command < file` - Read input from a file.

### Pipes
- `command1 | command2` - Pipe the output of `command1` as input to `command2`.

### Conditional Execution
- `command1 && command2` - Execute `command2` only if `command1` succeeds.
- `command1 || command2` - Execute `command2` only if `command1` fails.

### Process Management
- `ps` - List running processes.
- `kill` - Terminate a process.
- `bg` - Put a process in the background.
- `fg` - Bring a background process to the foreground.

