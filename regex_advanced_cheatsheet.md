Advanced PCRE (Perl Compatible Regular Expressions) regex cheat sheet with more complex patterns and techniques:

### Advanced Syntax:
- `(?:...)`: Non-capturing group (group that's not included in the match result).
- `(?=...)`: Positive lookahead assertion (matches a group only if it's followed by a specific pattern).
- `(?!...)`: Negative lookahead assertion (matches a group only if it's not followed by a specific pattern).
- `(?<=...)`: Positive lookbehind assertion (matches a group only if it's preceded by a specific pattern).
- `(?<!...)`: Negative lookbehind assertion (matches a group only if it's not preceded by a specific pattern).
- `(?i)`: Inline case-insensitive flag (applies case-insensitivity to a specific portion of the regex).
- `(*VERB)`: Various verbs for advanced control (e.g., `(*SKIP)`, `(*THEN)`).

### Advanced Quantifiers:
- `*?`, `+?`, `??`, `{n,}?`: Lazy quantifiers (matches as few characters as possible).
- `*+`, `++`, `?+`, `{n,}+`: Possessive quantifiers (prevent backtracking).

### Capture and Backreference:
- `(...)` (or `()`) for capturing groups.
- `\1`, `\2`, etc.: Backreferences to captured groups (e.g., `\1` references the first captured group).
- `(?|...)`: Reset capture group numbering in a branch reset group.

### Named Capture Groups:
- `(?<name>...)`: Named capture group.
- `(?P<name>...)`: Named capture group (alternative syntax).

### Unicode and Character Properties:
- `\p{Property=Value}`: Match characters with specific Unicode properties (e.g., `\p{Script=Latin}`).
- `\X`: Match an extended Unicode sequence (combining characters).

### Substitution:
- `preg_replace(pattern, replacement, subject)`: Substitution in PHP using PCRE.

### Recursive Patterns:
- `(?R)`: Recurse the entire pattern.
- `(?1)`, `(?2)`, etc.: Recurse a specific capturing group.
- `(?R)`, `(?&name)`: Recurse a named capturing group.

### Conditional Matching:
- `(?(condition)true|false)`: Conditional match (matches 'true' if 'condition' is true, otherwise 'false').

### Mode Modifiers:
- `(?ismx)` at the start of the pattern: Set options for the entire pattern (i.e., `i` for case-insensitive, `s` for single-line, `m` for multi-line, `x` for extended).

### Examples:
1. Match HTML tags and capture their content:
   ```regex
   <([^>]+)>(.*?)<\/\1>
   ```

2. Match and extract IPv4 addresses:
   ```regex
   \b\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}\b
   ```

3. Match and capture quoted strings (allowing for escaped quotes):
   ```regex
   "([^"\\]*(\\.[^"\\]*)*)"
   ```

4. Match a valid credit card number using lookahead:
   ```regex
   (?!.*(\d)(-?\1){3,})(\d{4}-?){3}\d{4}
   ```

5. Match a valid time in 24-hour format:
   ```regex
   ([01]?[0-9]|2[0-3]):[0-5][0-9]
   ```
