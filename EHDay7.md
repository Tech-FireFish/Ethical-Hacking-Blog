### 🔢 Numeric Operators (Integers Only)
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `-eq` | **Eq**ual to | `[[ "$num" -eq 10 ]]` |
| `-ne` | **N**ot **e**qual to | `[[ "$num" -ne 10 ]]` |
| `-gt` | **G**reater **t**han | `[[ "$num" -gt 10 ]]` |
| `-ge` | **G**reater than or **e**qual to | `[[ "$num" -ge 10 ]]` |
| `-lt` | **L**ess **t**han | `[[ "$num" -lt 10 ]]` |
| `-le` | **L**ess than or **e**qual to | `[[ "$num" -le 10 ]]` |




---
### 🔤 String Operators
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `=` or `==` | Strings are equal | `[[ "$str" == "hello" ]]` |
| `!=` | Strings are not equal | `[[ "$str" != "hello" ]]` |
| `-z` | String is **empty** (Zero length) | `[[ -z "$str" ]]` |
| `-n` | String is **not empty** (Non-zero length) | `[[ -n "$str" ]]` |
| `=~` | Matches a **Regular Expression** | `[[ "$str" =~ ^[0-9]+$ ]]` |### 🔢 Numeric Operators (Integers Only)
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `-eq` | **Eq**ual to | `[[ "$num" -eq 10 ]]` |
| `-ne` | **N**ot **e**qual to | `[[ "$num" -ne 10 ]]` |
| `-gt` | **G**reater **t**han | `[[ "$num" -gt 10 ]]` |
| `-ge` | **G**reater than or **e**qual to | `[[ "$num" -ge 10 ]]` |
| `-lt` | **L**ess **t**han | `[[ "$num" -lt 10 ]]` |
| `-le` | **L**ess than or **e**qual to | `[[ "$num" -le 10 ]]` |




---
### 🔤 String Operators
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `=` or `==` | Strings are equal | `[[ "$str" == "hello" ]]` |
| `!=` | Strings are not equal | `[[ "$str" != "hello" ]]` |
| `-z` | String is **empty** (Zero length) | `[[ -z "$str" ]]` |
| `-n` | String is **not empty** (Non-zero length) | `[[ -n "$str" ]]` |
| `=~` | Matches a **Regular Expression** | `[[ "$str" =~ ^[0-9]+$ ]]` |




---
---
### 🔗 Logical Operators (Combining Conditions)
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `&&` | Logical **AND** (Both must be true) | `[[ "$age" -gt 18 && "$status" == "active" ]]` |
| `||` | Logical **OR** (At least one must be true) | `[[ "$role" == "admin" || "$role" == "root" ]]` |
| `!` | Logical **NOT** (Inverts the result) | `[[ ! -d "backup_dir" ]]` |





---
---
### 🔗 Logical Operators (Combining Conditions)
| Operator | Meaning | Example |
| :--- | :--- | :--- |
| `&&` | Logical **AND** (Both must be true) | `[[ "$age" -gt 18 && "$status" == "active" ]]` |
| `||` | Logical **OR** (At least one must be true) | `[[ "$role" == "admin" || "$role" == "root" ]]` |
| `!` | Logical **NOT** (Inverts the result) | `[[ ! -d "backup_dir" ]]` |
