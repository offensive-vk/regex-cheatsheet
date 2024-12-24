# ✨ Comprehensive Regex Cheat Sheet  

This is my custom regex cheatsheet that I will use to remember &rarr; "how to write regex easily" for future purposes only. [*]

## 🔍 What is Regex?  

Regex (short for **Regular Expressions**) is a powerful tool for pattern matching and string manipulation. It allows you to define search patterns to match, extract, replace, or validate text based on specific criteria. Regex is commonly used in programming, data validation, text processing, and more.

## 🔤 Regex Wildcard Characters and Symbols  

| **Character**   | **Example**       | **Description**                                                                 |
|------------------|-------------------|---------------------------------------------------------------------------------|
| `.`              | `a.b`             | Matches any single character except a newline.                                  |
| `^`              | `^start`          | Matches the beginning of a string.                                              |
| `$`              | `end$`            | Matches the end of a string.                                                    |
| `*`              | `a*`              | Matches zero or more occurrences of the preceding character.                    |
| `+`              | `a+`              | Matches one or more occurrences of the preceding character.                     |
| `?`              | `a?`              | Matches zero or one occurrence of the preceding character.                      |
| `{n}`            | `a{3}`            | Matches exactly `n` occurrences of the preceding character.                     |
| `{n,}`           | `a{2,}`           | Matches `n` or more occurrences of the preceding character.                     |
| `{n,m}`          | `a{2,4}`          | Matches between `n` and `m` occurrences of the preceding character.             |
| `|`              | `a` | `b`         | Matches either `a` or `b`.                                                      |
| `[]`             | `[a-z]`           | Matches any character in the set or range.                                      |
| `[^]`            | `[^a-z]`          | Matches any character not in the set or range.                                  |
| `()`             | `(abc)`           | Groups expressions or captures the matched text.                                |
| `(?:)`           | `(?:abc)`         | Groups expressions without capturing the matched text.                          |
| `\`              | `\d`              | Escapes special characters or defines shorthand character classes.              |
| `\d`             | `\d`              | Matches any digit (equivalent to `[0-9]`).                                      |
| `\D`             | `\D`              | Matches any non-digit character.                                                |
| `\w`             | `\w`              | Matches any word character (alphanumeric or `_`).                              |
| `\W`             | `\W`              | Matches any non-word character.                                                |
| `\s`             | `\s`              | Matches any whitespace character (spaces, tabs, line breaks).                  |
| `\S`             | `\S`              | Matches any non-whitespace character.                                          |
| `\b`             | `\bword\b`        | Matches a word boundary.                                                       |
| `\B`             | `\Bword`          | Matches a position that is not a word boundary.                                |
| `\n`             | `line1\nline2`    | Matches a newline character.                                                   |
| `\t`             | `\t`              | Matches a tab character.                                                       |

## 🚩 Regex Flags  

| **Flag** | **Description**                                    |
|----------|----------------------------------------------------|
| `i`      | Case-insensitive matching.                        |
| `g`      | Global search (find all matches).                 |
| `m`      | Multiline mode (`^` and `$` match line starts/ends). |
| `s`      | Allows `.` to match newline characters.           |
| `u`      | Enables Unicode matching.                        |
| `y`      | Sticky matching (match at the exact position).   |

## 🌟 Top 20 Popular Regex Patterns  

1. **Email Validation**  
   - **Pattern**: `/^[\w.%+-]+@[A-Za-z0-9.-]+\.[A-Z]{2,}$/i`  
   - **Explanation**: Matches a valid email format.  
   - **Example**: `test.email+regex@gmail.com` ✅  

2. **URL Validation**  
   - **Pattern**: `/^(https?:\/\/)?([\w\-]+\.)+[a-z]{2,}(:\d+)?(\/[^\s]*)?$/i`  
   - **Explanation**: Matches URLs, including `http`, `https`, and optional paths.  
   - **Example**: `https://example.com/path` ✅  

3. **Phone Number**  
   - **Pattern**: `/^\+?[1-9]\d{1,14}$/`  
   - **Explanation**: Matches international phone numbers.  
   - **Example**: `+1234567890` ✅  

4. **Date (YYYY-MM-DD)**  
   - **Pattern**: `/^\d{4}-\d{2}-\d{2}$/`  
   - **Explanation**: Matches a date format with dashes.  
   - **Example**: `2024-12-24` ✅  

5. **Hexadecimal Color**  
   - **Pattern**: `/^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/`  
   - **Explanation**: Matches hex color codes.  
   - **Example**: `#FF5733` ✅  

6. **Password Validation**  
   - **Pattern**: `/^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/`  
   - **Explanation**: At least 8 characters, 1 letter, and 1 number.  
   - **Example**: `Passw0rd` ✅  

7. **Whitespace Trimmer**  
   - **Pattern**: `/^\s+|\s+$/g`  
   - **Explanation**: Removes leading and trailing spaces.  
   - **Example**: `"  hello  " -> "hello"` ✅  

8. **IPv4 Address**  
   - **Pattern**: `/^(\d{1,3}\.){3}\d{1,3}$/`  
   - **Explanation**: Matches IPv4 addresses.  
   - **Example**: `192.168.1.1` ✅  

9. **Only Numbers**  
   - **Pattern**: `/^\d+$/`  
   - **Explanation**: Matches strings containing only digits.  
   - **Example**: `123456` ✅  

10. **Only Alphabets**  
    - **Pattern**: `/^[A-Za-z]+$/`  
    - **Explanation**: Matches strings containing only letters.  
    - **Example**: `HelloWorld` ✅  

11. **Alphanumeric Strings**  
    - **Pattern**: `/^[A-Za-z0-9]+$/`  
    - **Explanation**: Matches strings containing only letters and numbers.  
    - **Example**: `Test123` ✅  

12. **US Zip Code**  
    - **Pattern**: `/^\d{5}(-\d{4})?$/`  
    - **Explanation**: Matches US zip codes with optional 4-digit extension.  
    - **Example**: `12345-6789` ✅  

13. **HTML Tags**  
    - **Pattern**: `/^<\/?[a-z][a-z0-9]*[^<>]*>$/i`  
    - **Explanation**: Matches basic HTML tags.  
    - **Example**: `<div>` ✅  

14. **Duplicate Words**  
    - **Pattern**: `/\b(\w+)\s+\1\b/`  
    - **Explanation**: Matches duplicate consecutive words.  
    - **Example**: `"hello hello"` ✅  

15. **Floating Point Numbers**  
    - **Pattern**: `/^[+-]?\d*\.?\d+$/`  
    - **Explanation**: Matches floating-point numbers.  
    - **Example**: `3.14` ✅  

16. **Non-ASCII Characters**  
    - **Pattern**: `/[^\x00-\x7F]+/`  
    - **Explanation**: Matches non-ASCII characters.  
    - **Example**: `你好` ✅  

17. **Social Security Number (SSN)**  
    - **Pattern**: `/^\d{3}-\d{2}-\d{4}$/`  
    - **Explanation**: Matches US SSN format.  
    - **Example**: `123-45-6789` ✅  

18. **Trailing Comma Remover**  
    - **Pattern**: `/,\s*$/`  
    - **Explanation**: Removes trailing commas from strings.  
    - **Example**: `"hello," -> "hello"` ✅  

19. **Camel Case Words**  
    - **Pattern**: `/([a-z]+)([A-Z][a-z]+)/g`  
    - **Explanation**: Matches camelCase words.  
    - **Example**: `camelCase` ✅  

20. **Credit Card Numbers**  
    - **Pattern**: `/^\d{4}-?\d{4}-?\d{4}-?\d{4}$/`  
    - **Explanation**: Matches credit card numbers with or without dashes.  
    - **Example**: `1234-5678-9012-3456` ✅  

***

<p align="center">
  <i>&copy; <a href="https://github.com/offensive-vk/">Vedansh </a> 2020 - Present</i><br>
  <i>Licensed under <a href="https://github.com/offensive-vk/">Mine</a></i><br>
  <a href="https://github.com/TheHamsterBot"><img src="https://i.ibb.co/4KtpYxb/octocat-clean-mini.png" alt="hamster"/></a><br>
  <sup>Thanks for visiting :)</sup>
</p>
