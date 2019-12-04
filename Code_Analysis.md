# Code Analysis for Software Security Engineering

##TODO Remove later
![Not having good time](https://i.kym-cdn.com/entries/icons/mobile/000/028/539/DyqSKoaX4AATc2G.jpg)

## Code Review Strategy



## Manual Code Review


## Automated Tool Findings

### Codacy
#### Overview
- Codacy Report (*Click link for full report*) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/69a6958fd1f04bc98d8e581ce786f754)](https://www.codacy.com?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=akbarber/clonexbmc&amp;utm_campaign=Badge_Grade)
- Total Issues: 2543
- Issue Categories:
  - Security: 415
  - Error Prone: 348
  - Code Style: 1506
  - Compatibility: 1
  - Unused Code: 3
  - Performance: 270
- Overall code grade: A
- Levels for Security Issues
  - Info: The least critical issue type will appear as **blue**; for example code style issues are shown this way.
  - Warning: This issue type will appear as **yellow**. You should be careful with these ones, they are based on code standards and conventions.
  - Error: The more dangerous types of issues will show as **red**. Take your time to fix these, although the code may run, these issues show the code that is very susceptible to problems. These issues are bug-prone, and/or can have serious problems regarding security and compatibility.

#### Key Findings
- [CWE–126](https://cwe.mitre.org/data/definitions/126.html) (Buffer Over-read) – **206**
  - **201** – *strlen()* - Does not handle strings that are not \0-terminated; if given one it may perform an over-read (it could cause a crash if unprotected)
  - **5** – *wcslen()* -	Does not handle strings that are not \0-terminated; if given one it may perform an over-read (it could cause a crash if unprotected)
  
- [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow) – **101** 
  - **94** – *strcpty()* -	Easily used incorrectly; doesn't always \0-terminate or check for invalid pointers [MS-banned]
  - **6** – *strncat()* -	Easily used incorrectly (e.g., incorrectly computing the correct maximum size to add) [MS-banned] Consider strcat_s, strlcat, snprintf, or automatically resizing strings.
  - **1** – *wcsncpy()* -	Easily used incorrectly; doesn't always \0-terminate or check for invalid pointers [MS-banned]
  
 - [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow)/[CWE – 20](https://cwe.mitre.org/data/definitions/20.html) (Improper Input Validation) – **23**
  - **22** – *read()* -	Check buffer boundaries if used in a loop including recursive loops
  - **1** – *getc()* -	Check buffer boundaries if used in a loop including recursive loops

- [CWE–676]( https://cwe.mitre.org/data/definitions/676.html) (Use of Potentially Dangerous Function) - **15**
  - **15** – *usleep()* -	This C routine is considered obsolete (as opposed to the shell command by the same name). The interaction of this function with SIGALRM and other timer functions such as sleep(), alarm(), setitimer(), and nanosleep() is unspecified (CWE-676). Use nanosleep(2) or setitimer(2) instead.
- [CWE–478](https://cwe.mitre.org/data/definitions/478.html)   ??
- [CWE–391](https://cwe.mitre.org/data/definitions/391.html) (Unchecked Error Condition)– **1** 
  - **1** – *“catch”* clause - Handle the exception or explain in a comment why it can be ignored.
- [CWE–563](https://cwe.mitre.org/data/definitions/563.html) (Assignment to Variable without Use) – **2** 
  - **2** – *“offset”* variable -	Remove this useless assignment to local variable 'offset'.



## Summary of Key Findings

## OSS Pull Requests???

## Team Reflection and GitHub Link

This time around, it was difficult to find time to meet together as a group to fully access and delegate tasks for the other group members. The Thanksgiving break, along with the holiday season in general, were the main reasons for this issue. In addition, we group members had difficulty in finding and implementing different analysis tools available for public use to access the Kodi software and other relevant libraries. Trial and error was needed, but we can all agree that the effort helped us learn. Our individual members tried their best for this deliverable, and hope to wrap things up well for the upcoming presentation. 

## [GitHub Repository](https://github.com/mroejr/BAAM/projects/6)
