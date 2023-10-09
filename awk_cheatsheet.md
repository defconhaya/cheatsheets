
**Basic AWK Syntax:**
```
awk 'pattern { action }' input_file
```

- `pattern`: A condition that specifies when to perform the action.
- `{ action }`: The code block to be executed when the pattern matches.

**Common AWK Commands:**

1. **Printing:**

   - Print the entire line:
     ```
     awk '{ print }' input_file
     ```

   - Print specific columns:
     ```
     awk '{ print $2, $4 }' input_file
     ```

2. **Patterns and Conditions:**

   - Print lines that match a specific pattern (e.g., lines containing "search"):
     ```
     awk '/search/ { print }' input_file
     ```

   - Print lines that match a condition (e.g., lines with the second field greater than 10):
     ```
     awk '$2 > 10 { print }' input_file
     ```

3. **Built-in Variables:**

   - `NF`: Number of fields in the current line.
     ```
     awk 'NF > 3 { print }' input_file
     ```

   - `NR`: Record (line) number.
     ```
     awk 'NR == 5 { print }' input_file
     ```

   - `FS`: Field separator (default is whitespace).
     ```
     awk -F',' '{ print $1 }' input_file
     ```

4. **Math and Arithmetic:**

   - Perform calculations (e.g., sum of column 3):
     ```
     awk '{ sum += $3 } END { print sum }' input_file
     ```

5. **String Functions:**

   - Concatenate fields:
     ```
     awk '{ print $1 $2 }' input_file
     ```

   - Find and replace:
     ```
     awk '{ gsub("old", "new"); print }' input_file
     ```

6. **Control Flow:**

   - Use if-else conditions:
     ```
     awk '{ if ($3 > 10) print "High"; else print "Low" }' input_file
     ```

7. **Output Formatting:**

   - Specify the output field separator and format:
     ```
     awk 'BEGIN { OFS="\t" } { print $1, $2 }' input_file
     ```

8. **File Reading and Processing:**

   - Process multiple input files:
     ```
     awk '{ print FILENAME, $0 }' file1.txt file2.txt
     ```

   - Use `next` to skip processing of specific lines:
     ```
     awk '/skip_pattern/ { next } { print }' input_file
     ```

9. **User-Defined Functions:**

   - Define and use custom functions:
     ```
     awk 'function myfunc(x) { return x * 2 } { print myfunc($3) }' input_file
     ```

**Advanced AWK:**

- **Arrays:** AWK supports arrays, which can be used to store and manipulate data.

- **Regular Expressions:** Powerful pattern matching and manipulation using regular expressions.

- **Output Formatting:** Control the formatting of printed output with `printf`.

- **Reading from Pipes and Redirecting Output:** AWK can read from pipes and redirect its output.

- **Advanced Scripting:** AWK can be used to write complex scripts for data processing tasks.
