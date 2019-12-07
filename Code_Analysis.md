# Code Analysis for Software Security Engineering


## Code Review Strategy

In analyzing the Kodi codebase, it felt very daunting to try to analyze the codebase as there were over 100,000 lines of code. The project was primarily written in C/C++, and it seemed there were many automated tools available to analyze the codebase. Though, with available tools, we were concerned about the ease-of-use of the tools, and if it was easy to analyze and summarize.
Following the automated tools, the next focus would be the manual code review.

* Define the scope of the analysis 
 * Determine the correct static tools that will be used for the review.
  * Have the tools review files that have been identified throughout this course.
  * Review the reports and find commin results.
 * Analyze manual code on a high-level and flag areas of interest. 
  * Validate flagged areas with the tools that were ran.
 * Compile a pull request of any code that has been determined a clear vulnerability.

## Manual Code Review

Code that was reviewed
 * [PlayList](https://github.com/xbmc/xbmc/blob/master/xbmc/playlists/PlayList.cpp)
 * [PVR](https://github.com/xbmc/xbmc/blob/master/xbmc/pvr/PVRDatabase.cpp)
 * [Application](https://github.com/xbmc/xbmc/blob/master/xbmc/Application.cpp)
 
These are the code sections that we have done most of our project with and flet that we would have a better understanding of walking through this code over any other sections. Theses sections are written in C++ and having an understanding of C and staying with the code that we've seen a few times in the project is how we moved foward. The code is listed in the order that it was reviewed and the scope of the review is to look for CWEs that were discussed and reviewed in class.

[PlayList](https://github.com/xbmc/xbmc/blob/master/xbmc/playlists/PlayList.cpp)  
Atfer reviewing the code for this section there are two CWEs that have a clear presence in a few parts of the code. In the code in this section there are no input validation occurring anywhere that would have me believe that the CWE 20 would be violated in this section. In the same parts of the code that I feel have the CWE 20, I would say the same would need to be said about the CWE 120. There is no code that addresses bounds in any of the arrays that are implemented in the code. Leading me to believe that CWE 120 is also violated in the same sections of the code.

[PVR](https://github.com/xbmc/xbmc/blob/master/xbmc/pvr/PVRDatabase.cpp)  
The first two code reviews have a lot of code that are doing the same things. In PlayList the code is setting up list of arrays and in that code it was found that no input validation or bounds were being checked. The PVR section is in most part doing the same things and still not addressing any of the same concerns as the review section. It could be said that both sections violate CWE 20, CWE 120 in the same manner. These sections were chosen because the group have discussed in a few different ways and felt that we had a good understanding of how the code was working and what should be expected. At the onset we did not know that both sections would have the same code violations in the same manner.

[Application](https://github.com/xbmc/xbmc/blob/master/xbmc/Application.cpp)  
 This section was more of a daunting task for the simple fact that this code covers all aspects of the application. Knowing that CWE 20 and CWE 120 should be reported the serach for new CWE was the set task in this section. There were two other CWEs that could be on this section of code. In this section of code the srand is used with no regard for security and passwords are in no shape or form encrypted or hidden. I do believe that these are different CWEs and should be reported as CWE 327 and CWE 311 for a total of 4 CWE's in this section.

The group took the findings of the manual review and collated them with the two static tools that were ran on the code. The finds of the manual review didn't match up line for line across the tools, but the fact that CWE 120 was found when Kodi called the arrays should have a clear indication that if the array was constructed with both input validation and some form of bounds checking that this wouldn't be a worry. There should be three ways that this could be addressed in the code. The first being to have the checks in a if statement as the arrays are in construction, the second would be to have the checks in a header have have the check called across all code for Kodi and would be more beneficial for all code. The last would be to create a function that is called and this would lead to code needed to be written throughout the project and not being a clean, secure, or efficient way to fix this.

## Automated Tool Findings

### Codacy

#### Overview

[Codacy]( https://www.codacy.com/) is an automated application that automatically identifies issues through static code review analysis. You can get notified on security issues, code coverage, code duplication, and code complexity in every commit and pull request, directly from your current workflow.

- Codacy Report for Cloned Kodi Repository (*Click Link for Full Report*) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/5ce9f98dbd9a4ea1b79e0240195dc058)](https://www.codacy.com/manual/akbarber/xmbcclone?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=akbarber/xmbcclone&amp;utm_campaign=Badge_Grade)
- Total Issues: 2544
* Issue Categories:
  * Security: 416 
  * Error Prone: 348
  * Code Style: 1506
  * Compatibility: 1
  * Unused Code: 3
  * Performance: 270
- Overall code grade: A
- Levels for Security Issues
  - Info: The least critical issue type will appear as **blue** (in the report link); for example code style issues are shown this way.
  - Warning: This issue type will appear as **yellow** (in the report link). You should be careful with these ones, they are based on code standards and conventions.
  - Error: The more dangerous types of issues will show as **red** (in the report link). Take your time to fix these, although the code may run, these issues show the code that is very susceptible to problems. These issues are bug-prone, and/or can have serious problems regarding security and compatibility.

#### Key Findings

- [CWE–126](https://cwe.mitre.org/data/definitions/126.html) (Buffer Over-read) – **206**
  - **201** – *strlen()* - Does not handle strings that are not \0-terminated; if given one it may perform an over-read (it could cause a crash if unprotected)
  - **5** – *wcslen()* - Does not handle strings that are not \0-terminated; if given one it may perform an over-read (it could cause a crash if unprotected)
- [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow) – **101**
  - **94** – *strcpty()* - Easily used incorrectly; doesn't always \0-terminate or check for invalid pointers [MS-banned]
  - **6** – *strncat()* - Easily used incorrectly (e.g., incorrectly computing the correct maximum size to add) [MS-banned] Consider strcat_s, strlcat, snprintf, or automatically resizing strings.
  - **1** – *wcsncpy()* - Easily used incorrectly; doesn't always \0-terminate or check for invalid pointers [MS-banned]
- [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow)/[CWE–20](https://cwe.mitre.org/data/definitions/20.html) (Improper Input Validation) – **23**
  - **22** – *read()* - Check buffer boundaries if used in a loop including recursive loops
  - **1** – *getc()* - Check buffer boundaries if used in a loop including recursive loops
- [CWE–676]( https://cwe.mitre.org/data/definitions/676.html) (Use of Potentially Dangerous Function) - **15**
  - **15** – *usleep()* - This C routine is considered obsolete (as opposed to the shell command by the same name). The interaction of this function with SIGALRM and other timer functions such as sleep(), alarm(), setitimer(), and nanosleep() is unspecified (CWE-676). Use nanosleep(2) or setitimer(2) instead.
- [CWE–478](https://cwe.mitre.org/data/definitions/478.html) (Missing Default Case in Switch Statement)
  - **2** - *“switch”* statements - Add a 'default' clause to this 'switch' statement
- [CWE–391](https://cwe.mitre.org/data/definitions/391.html) (Unchecked Error Condition)– **1** 
  - **1** – *“catch”* clause - Handle the exception or explain in a comment why it can be ignored.
- [CWE–563](https://cwe.mitre.org/data/definitions/563.html) (Assignment to Variable without Use) – **2**
  - **2** – *“offset”* variable - Remove this useless assignment to local variable 'offset'.

### Flawfinder

#### Overview

[Flawfinder](https://dwheeler.com/flawfinder/) is a command-line tool used to review C/C++ code for any security vulnerabilities. The program itself is written in python. The program can observe individual files or entire directories for vulnerabilities. After printing results, the program states that not every hit is necessarily a security vulnerability, but other security vulnerabilities can exist.

![Sample](https://i.imgur.com/pWkbP6Q.png)

#### Key Findings

In using the tool, three directories were selected to run the tool against. Below are the results.

- \xbmc\xbmx\addons\
  - 177 hits
  - Listed vulnerabilities  
    - [CWE-78](https://cwe.mitre.org/data/definitions/78.html) (OS Command Injection)
    - [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow)
    - [CWE-134](https://cwe.mitre.org/data/definitions/134.html) (Use of Externally-Controlled Format String)
    - [CWE-807](https://cwe.mitre.org/data/definitions/807.html) (Reliance on Untrusted Inputs in a Security Decision)
    - [CWE-20](https://cwe.mitre.org/data/definitions/20.html) (Improper Input Validation)
    - [CWE-119](https://cwe.mitre.org/data/definitions/119.html) (Improper Restriction of Operations within the Bounds of a Memory Buffer)
    - [CWE-190](https://cwe.mitre.org/data/definitions/190.html) (Integer Overflow or Wraparound)
    - [CWE-362](https://cwe.mitre.org/data/definitions/362.html) (Race Condition)
    - [CWE–126](https://cwe.mitre.org/data/definitions/126.html) (Buffer Over-read)

- \xbmc\xbmc\pvr
  - 41 hits
  - Listed vulnerabilities  
    - [CWE-78](https://cwe.mitre.org/data/definitions/78.html) (OS Command Injection)
    - [CWE-190](https://cwe.mitre.org/data/definitions/190.html) (Integer Overflow or Wraparound)
    - [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow)
    - [CWE–126](https://cwe.mitre.org/data/definitions/126.html) (Buffer Over-read)

- \xbmc\xbmc\video
  - 61 hits
  - Listed vulnerabilities
    - [CWE–120](https://cwe.mitre.org/data/definitions/120.html) (Buffer Overflow)
    - [CWE-119](https://cwe.mitre.org/data/definitions/119.html) (Improper Restriction of Operations within the Bounds of a Memory Buffer)
    - [CWE-190](https://cwe.mitre.org/data/definitions/190.html) (Integer Overflow or Wraparound)

## Summary of Key Findings



Out of the 416 security issues from the findings of the automated tool, Codacy, most were mapped to CWEs, however many of the Warning Level issues did not have clear CWE. Even though there were not specific CWEs that could be assigned, Codacy did have suggested coding practices for the some of issues which can be seen in the report link above. For the security issue in the Information category, there were a total of 343 issues, in the Warning category there were 70 issues, and in the Error category there were 3 issues. After some investigation we believe two of the three Error issues were from a portion of the repository for test code from lib/libUPnP/Platinum/Build/Targets/x86-microsoft-win32-vs2010/Platinum.Managed.MediaServerTest/Program.cs(line 37) and lib/libUPnP/Platinum/Build/Targets/x86-microsoft-win32-vs2010/Platinum.Managed.SsdpTest/Program.cs(line 38). If these are legitimate code then their potential security risks are within switch statements shown above. For the one Error we believe to be legitimate came from tools/EventClients/lib/c#/EventClient.cs (line 158).

![CodeExample](https://i.imgur.com/scc4dDz.png)

The report states "When exceptions occur, it is usually a bad idea to simply ignore them. Instead, it is better to handle them properly, or at least to log them". This issue can be mapped to CWE-391 (Unchecked Error Condition) stating that by ignoring expections and other error conditions this may allow attackers to go unnoticed when inducing unexpected behavior.

In the Codacy report there is also a section on Security Monitoring that checks for issues in 19 categories such as XSS, Input Validation, File Access, etc. In the report it can be seen that all of the categories have a green checkmark indicating there were not issues found in thoses category. We are still working on understanding this part of the tool as it shows in the Security Monitoring section that there are no security issues in the Input Validation category when in fact there were 23.

In using Flawfinder, there were troubles in trying to analyze the entire Kodi codebase, as some errors would occur when running the python script. This was not at fault with the codebase, but with the installation of Python on the machine. Rather than spend too much time troubleshooting this error, it was decided to just analyze directories of the xmbc\ codebase.

When using the command line tool, Flawfinder, it will list the specific file and line that a potential vulnerability was found, along with a the vulnerability's details. Below is an example of this after running the python script.

![Example](https://i.imgur.com/GKfVJtK.png)

We had tried another tool Called SonarCloud. The tool also gave the code a passing grade. We did not have enough time to completely analyze SonarCloud’s results but we noticed that this tool showed a quite a few different CWEs than the other tools. SonarCloud results stated that there were no vulnerabilities but there were 225 “Security Hotspots” meaning there are not necessarily issues but they need to be reviewed to make sure there are not vulnerabilities. This does, in our opinion, link up with the other tools as most of the hits were warnings that needed to be reviewed, not straight forward vulnerabilities. 

![SonarCloudgrade](https://i.imgur.com/GmBFmqz.png)


![SonarCloud](https://i.imgur.com/DIhu535.png)


With the information provided from the tools we were able to narrow down a few security weakness to focus our manual review to. The top three weakness we found were CWE-126 (Buffer Over-read), CWE-120 (Buffer Overflow), and CWE-20 (Improper Input Validation).

## OSS Pull Request

The team has open an issue on the Kodi form, because discussion of your code is the first step in getting a pull request completed. This page will be updated as we walk through the steps with Kodi.



## Team Reflection and GitHub Link

This time around, it was difficult to find time to meet together as a group to fully access and delegate tasks for the other group members. The Thanksgiving break, along with the holiday season in general, were the main reasons for this issue. In addition, we group members had difficulty in finding and implementing different analysis tools available for public use to access the Kodi software and other relevant libraries. Trial and error was needed, but we can all agree that the effort helped us learn. Our individual members tried their best for this deliverable, and hope to wrap things up well for the upcoming presentation.

## [GitHub Repository](https://github.com/mroejr/BAAM/projects/6)
