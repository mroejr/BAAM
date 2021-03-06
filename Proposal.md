# Kodi Project Proposal

## Operational Environment

The environment this project chooses to focus on is a home environment. The software would be used for personal use. 

## Security needs
_Note: The security needs listed here is under the presumption that Kodi will be used as intended without 3rd party add-ons, pirated content, or any other illegal uses._
- Privacy
  - User's streaming habits should not be shared without the User's permission or consent
- Secure add-ons
  - Add-ons should be legitimate and without malicious content
  - Add-ons should be regularly updated
- Secure communication
  - If a user is using a personal media server, such as Plex server, to stream content to their Kodi software, it is expected to have a secure communication channel

## Security features of Kodi

- Code changes are verified with the use of [checksum](https://kodi.wiki/view/Creating_and_using_edid.bin_via_xorg.conf). 
- Only keeps event logs for the curent session.
- Makes users aware of [Banned Add-ons](https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons#top). 
- Capable of using a [NAS](https://kodi.wiki/view/NAS) to hold video and audio data.
- Kodi asks its users to [participate](https://github.com/xbmc/xbmc/blob/master/privacy-policy.txt) in any data collection.
- Kodi uses [JSON-RPC API](https://www.jsonrpc.org/specification) for data communication.

## Motivation Behind Kodi

Cable/Satellite services for Television broadcasting has been in a decline since the introduction of popular streaming apps such as Netflix and Hulu. Some TV manufacturers have introduced Smart TVs with few of these streaming apps pre-built. Along with the growth of Smart TVs came along streaming devices such as Google's Chromecast, Apple TV, and Roku.

Kodi is an open-source entertainment hub that is customizable and available on various devices and operating systems. This includes Microsoft Windows, Apple OSX and iOS, Android, Linux, and Raspberry Pi. Kodi uses a lot when it comes to its add-on, a potential media server, live-TV apps, etc. However, with the variety of uses on Kodi, there are diverse point of security that should be considered. Is any data collected from the user's streaming/viewing habits? How is information communicated when using the Internet for various tasks? These are the types of questions the project members would want to investigate further and look for any flaws.

## Open Source Description of Kodi
- Kodi is an open-source entertainment hub
  - A media player than can refer to a media server for playing music, movies, TV shows, etc.
  - Features Add-ons to add to the entertainment hub
    - Music (Radio apps, Apple iTunes podcasts, etc.), Photo (iPhoto, OneDrive, etc.) and others
  - Kodi does not directly provide streaming apps such as Netflex or Hulu. Users would have to use third-party installers, which is not recommended from Kodi
  - Kodi is legal when used for its intended purposes
- Activity
  - Contributors – 600+
  - Commits – 53,000+
  - Last commit – 09/09/2019
  - Most recent pull request 09/09/2019
  - Most recent issue opened 09/09/2019
- Popularity
  - Statistics on the number of downloads or users is unavailable, but Kodi is talked about in present time on popular journal sites such as [PCMag](https://www.pcmag.com/article/357106/what-is-kodi) and [Express](https://www.express.co.uk/life-style/science-technology/943451/Kodi-Add-On-Arrest-Fine-Popular)
- Languages used
  - C++ (88.0%), C (2.6%), and JavaScript (2.5%)
  - Other languages used but in significantly smaller proportions
- Platform(s)
  - Available on different operating systems and hardware platforms including: Windows, Apple OSX and iOS, Android, Linux, and Raspberry Pi
## License
  - Kodi's licensed is under the [GNU General Public LIcense v2.0 or later](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)
  - The overall project of Kodi also contains files and code licensed under different licenses:
    - [BSD-3-Clause](https://github.com/xbmc/xbmc/blob/master/LICENSES/BSD-3-Clause)
    - [BSD-4-Clause](https://github.com/xbmc/xbmc/blob/master/LICENSES/BSD-4-Clause)
    - [GPL-2.0-only](https://github.com/xbmc/xbmc/blob/master/LICENSES/GPL-2.0-only)
    - [GPL-2.0-or-later](https://github.com/xbmc/xbmc/blob/master/LICENSES/GPL-2.0-or-later)
    - [LGPL-2.1-or-later](https://github.com/xbmc/xbmc/blob/master/LICENSES/LGPL-2.1-or-later)
    - [MIT](https://github.com/xbmc/xbmc/blob/master/LICENSES/MIT)
    - [Unlicense (Public Domain)](https://github.com/xbmc/xbmc/blob/master/LICENSES/Unlicense)
## How to Contribute 
  - Coding
    - Fixing bugs
    - Adding features
  - Helping Kodi
    - Answering questions in the [support forums](https://forum.kodi.tv/).
    - Be supportive of new users.
  - Localization
    - Help translate Kodi into a native language.
  - Add-ons
    - Help code new [add-ons](https://kodi.tv/create-an-addon).
  - Documentation
    - Help with writing new content or correcting existing material.
## Contributor agreement
  - Code will be free of copyright infringements 
  - Follow [code guidelines](https://github.com/xbmc/xbmc/blob/master/docs/CODE_GUIDELINES.md) 
  - Proper code documentation  
  - Code has passed testing on development platform
    - Kodi's [continuous integration system](https://jenkins.kodi.tv/) builds the pull request automatically. Contributors are expected to test the code on your development platform.
  - Team-Kodi Members should strive to:  
    - Promote open source 
    - Promote the sharing of knowledge and collaboration
    - Understand that development is a team effort
    - Apply the Law of Diminishing Return
    - Try to make all code, feature, and functions to be platform agnostic

## Security-related history

The Kodi project is actively maintained as can been seen in the activity section. From what we were able to find there have been three documented vulnerabilites for Kodi showing on [CVE details](https://www.cvedetails.com/vulnerability-list/vendor_id-16145/product_id-36080/Kodi-Kodi.html). The most recent reported was from 04/18/18 (CVE-2018-8831) and is stated to be a persistent XSS vulnerability in Kodi through 17.6. This vulnerability allows execution of HTML/script code via the playlist. There were two other recent CVE, one on 02/28/2017 (CVE-2017-5982) for directory traversal in the Chorus2 2.4.2 add-on for Kodi and the other on 05/23/2017 (CVE-2017-8314), also for directory traversal, in the built-in Zip Extraction function in Kodi 17.1. Most of the CVE vulnerabilities have to deal with XSS, Directory Traversal and DoS. I found 4 CVE vulnerabilities with KODI and 7 with XBMC which is was it was formerly called. 

## Planning and Contribution
The team had a few discussion on our team Canvas discussion board, our team decided to work on Kodi for our OSS project.  As a team, we have worked together on our proposal in class, outside of class and on Github where commits can be viewed through our repository [BAAM](https://github.com/mroejr/BAAM/issues?q=is%3Aissue+is%3Aclosed). We will be assigning team members to issues for [Milestone 2](https://github.com/mroejr/BAAM/milestone/2) shortly. 

### Documentation sources
  - [GitHub](https://github.com/xbmc/xbmc/blob/master/README.md)
  - Kodi [Wiki](https://kodi.wiki/view/Main_Page) page

