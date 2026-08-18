---
title: "Regex Tutorial - How to write Regular Expressions"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/dsa/write-regular-expressions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Regex Tutorial - How to write Regular Expressions
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/write-regular-expressions/)

---

# Regex Tutorial - How to write Regular Expressions

A regular expression (regex) is a sequence of characters that defines a search pattern. It is mainly used for pattern matching in strings, such as finding, replacing, or validating text. Regex is supported in almost every programming language, including Python, Java, C++ and JavaScript.
Below image shows an example of a regular expression and explains its parts, helping you understand how filenames or patterns can be matched effectively.
![example_of_regular_expression](assets/example_of_regular_expression-0e22308998.webp)
Example of Regular Expression
This regex checks if a filename is valid, allowing letters, numbers, underscore, hyphens and ends with .jpg, .png or .gif. Example matches: file123.jpg, my-photo.png, logo\_1.gif.
**Examples:** Match a Filename Ending with .jpg, .png, or .gif
````cpp
#include <regex>
#include <iostream>
#include <string>
using namespace std;
int main() {
    regex pattern(R"(^[a-zA-Z0-9_-]+\.(jpg|png|gif)$)"); // Raw string literal for regex
    string filename = "file123.jpg";
    if (regex_match(filename, pattern)) {
        cout << "Valid image filename" << endl;
    } else {
        cout << "Invalid filename" << endl;
    }
    return 0;
}
````
````c
#include <stdio.h>
#include <string.h>
#include <regex.h>
int main() {
    regex_t regex;
    int reti;
    char msgbuf[100];
    reti = regcomp(&regex, "^[a-zA-Z0-9_-]+\.(jpg|png|gif)$", 0);
    if (reti) {
        fprintf(stderr, "Could not compile regex\n");
        return 1;
    }
    char *filename = "file123.jpg";
    reti = regexec(&regex, filename, 0, NULL, 0);
    if (!reti) {
        puts("Valid image filename");
    } else if (reti == REG_NOMATCH) {
        puts("Invalid filename");
    } else {
        regerror(reti, &regex, msgbuf, sizeof(msgbuf));
        fprintf(stderr, "Regex match failed: %s\n", msgbuf);
    }
    regfree(&regex);
    return 0;
}
````
````java
import java.util.regex.Pattern;
import java.util.regex.Matcher;
public class Main {
    public static void main(String[] args) {
        String pattern = "^[a-zA-Z0-9_-]+\.(jpg|png|gif)$";
        String filename = "file123.jpg";
        Pattern compiledPattern = Pattern.compile(pattern);
        Matcher matcher = compiledPattern.matcher(filename);
        if (matcher.matches()) {
            System.out.println("Valid image filename");
        } else {
            System.out.println("Invalid filename");
        }
    }
}
````
````python3
import re
pattern = r'^[a-zA-Z0-9_-]+\.(jpg|png|gif)$'
filename = "file123.jpg"
if re.match(pattern, filename):
    print("Valid image filename")
else:
    print("Invalid filename")
````
````csharp
using System;
using System.Text.RegularExpressions;
public class Program {
    public static void Main() {
        string pattern = "^[a-zA-Z0-9_-]+\.(jpg|png|gif)$";
        string filename = "file123.jpg";
        if (Regex.IsMatch(filename, pattern)) {
            Console.WriteLine("Valid image filename");
        } else {
            Console.WriteLine("Invalid filename");
        }
    }
}
````
````javascript
const pattern = /^[a-zA-Z0-9_-]+\.(jpg|png|gif)$/;
const filename = "file123.jpg";
if (pattern.test(filename)) {
    console.log('Valid image filename');
} else {
    console.log('Invalid filename');
}
````
## Importance of Regular Expression
1. **Efficient Pattern Matching:** Quickly search for specific patterns in text or data without manual checking.
2. **Data Validation:** Validate inputs like email addresses, phone numbers, URLs, and passwords.
3. **Text Manipulation:** Perform search-and-replace operations across files or datasets effectively.
4. **Automation in Analytics and Tools:** Used in tools like Google Analytics for URL matching and filtering.
5. **Cross-Platform Support:** Works across programming languages and editors such as Python, Java, Sublime Text, Notepad++, and Microsoft Word.
## Common Elements Used in Regular Expressions
Regular expressions are built using special symbols and characters. Below are the most commonly used regex elements explained with simple examples.
1. **Repeaters (  \*, +, and { } ):** Repeaters specify how many times the preceding character or group should appear.
2. **Asterisk symbol (\*):** Matches the preceding character 0 or more times.
> **Example:** The regular expression ab\*c will give ac, abc, abbc, abbbc….and so on
**3. The Plus symbol (+)**: Matches the preceding character 1 or more times.
> **Example:** The regular expression ab+c will give abc, abbc, abbbc, … and so on.
**4. The curly braces { … }:** Defines an exact or range of repetitions.
> **Example:** {{2}: exactly 2 times
>  {min,}: at least min times
>  {min,max}: between min and max times
**5. Wildcard (.):**Matches any single character except a newline.
> **Example:** Regular expression .\* will tell the computer that any character can be used any number of times.
**6. Optional character (?):** Matches 0 or 1 occurrence of the preceding character.
> **Example:** docx? matches doc and docx
**7. The caret ( ^ ) symbol**: Ensures the match starts **at the beginning** of the string.
> **Example :** ^\d{3} matches 901 in 901-333
**8.  The dollar ( $ ) symbol:** Ensures the match ends at the end of the string.
> **Example:** \d{3}$ matches 333 in 901-333
**9. Character Classes:** Match specific types of characters: 
> \s: whitespace
> \S: non-whitespace
> \d: digit
> \D: non-digit
> \w: word character (letters, digits, \_)
> \W: non-word character
> \b: word boundary
> **Example:** [abc] matches a, b, or c
**10. Negated Character Class ([^ ])**: Matches characters not listed in the brackets.
> **Example :** [^abc] -> matches any character except a, b, c
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/write-regular-expressions/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
