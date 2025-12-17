

# Poison_Null_Byte

## Methodology

To solve this challenge, I first took some time to understand what the Poison Null Byte vulnerability actually is and how it works. I learned that it relies on improper input validation, where a null byte (%00) can prematurely terminate a string during file handling.

After exploring the FTP page of OWASP Juice Shop, I noticed that the application only allowed downloading files wich were .md and pd. Any other file type was blocked by a server-side restriction.

By looking at a URL Encoding Table, I discovered that a double-encoded null byte (%2500) could be used to bypass the file extension filter.

The idea was simple: request a forbidden file, add an allowed extension after a poison null byte, and let the backend misinterpret the filename.
For example, instead of requesting a blocked file directly, I sent a request like:

![image](./assets/Poison.png)

This way i could download the easter egg.


## Vulnerability

**Type:** Improper Input Validation
**Component affected:** File handling / FTP download mechanism
**Severity:** Medium

## Risks

    This vulnerability allows an attacker to bypass file type restrictions and access sensitive files that were not meant to be exposed. In a real-world scenario, this could lead to the disclosure of internal configuration files, backups, logs, or source code.

## Actions

File access controls should never rely solely on file extensions provided by user input. The application should strictly validate and sanitize filenames server-side and reject any unexpected encoding or null byte sequences.


