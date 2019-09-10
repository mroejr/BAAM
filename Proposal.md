# Kodi Project Proposal

## Operational Environment

The environment this project chooses to focus on is a home environment. The software would be used for personal use. A simple hardware device (Windows, Mac, Raspberry Pi) would have Kodi installed.

## Security needs

- Typical use for home/personal use:
  - User puts (owned) ripped DVDs on server to stream content on Kodi
    - This server could be a plex server, but for scope reach prevention will not be looked into further
  - User adds streaming apps via add-ons
    - Cannot do this via Kodi directly
    - User would need to use zip installer
      - Example: To install Netflix, a user would need a Netflix zip folder and on Kodi software allow add-ons from unknown sources
      - This could be a threat environment, but more on the fault of the user, not Kodi
    - When using streaming apps such as Netflix and Hulu, a user would expect their login/password information, financial information used on the app, and their privacy/viewing habits to be protected
  
- What security user expects
- How is the users financial information encrypted?
- How is the user's privacy protected?
- Intended threat environment(s)

## Security features of Kodi

- Hashed or encrypted
- What 802.11 protocol is used

## Motivation Behind Kodi

Cable/Satellite services for Television broadcasting has been in a decline since the introduction of popular streaming apps such as Netflix and Hulu. Some TV manufacturers have introduced Smart TVs with few of these streaming apps pre-built. Along with the growth of Smart TVs came along streaming devices such as Google's Chromecast, Apple TV, and Roku.

Kodi is an open-source entertainment hub that is customizable and available on various devices and operating systems. This includes Microsoft Windows, Apple OSX and iOS, Android, Linux, and Raspberry Pi. Kodi uses a lot when it comes to streaming from added-on streaming apps (i.e. Netflix and Hulu), a media server, live-TV apps, etc. However, with the variety of uses on Kodi, there are diverse point of security that should be considered. How is financial information secured if the user has a paid subscription to Netflix? Is any data collected from the user's streaming/viewing habits? How is information communicated when using the Internet for various tasks? These are the types of questions the project members would want to investigate further and look for any flaws.

## Open Source Description of Kodi

- Kodi is an open-source entertainment hub
  - A media player than can refer to a media server for playing music, movies, TV shows, etc.
  - Features Add-ons to add to the entertainment hub
    - Music (Radio apps, Apple iTunes podcasts, etc.), Photo (iPhoto, OneDrive, etc.) and others
  - Installing streaming apps such as Netflix and Hulu are possible, but the process of installing streaming apps is dependent on the type of hardware/operating system Kodi is installed
  - Kodi is legal when used for its intended purposes
- 600+ contributors to the GitHub
- Activity
- Popularity
  - Statistics on the number of downloads or users is unavailable, but Kodi is talked about in present time on popular journal sites such as [PCMag](https://www.pcmag.com/article/357106/what-is-kodi) and [Express](https://www.express.co.uk/life-style/science-technology/943451/Kodi-Add-On-Arrest-Fine-Popular)
- Languages used
  - C++ (88.0%), C (2.6%), and JavaScript (2.5%)
  - Other languages used but in significantly smaller proportions
- Platform(s)
  - Available on different operating systems and hardware platforms including: Windows, Apple OSX and iOS, Android, Linux, and Raspberry Pi
- Documentation sources
  - [GitHub](https://github.com/xbmc/xbmc/blob/master/README.md)
  - Kodi [Wiki](https://kodi.wiki/view/Main_Page) page

## Security-related history

- Known vulnerabilities
- Security related engineering decisions
- Security feature additions/removal
