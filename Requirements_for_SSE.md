# Requirements for Software Security Engineering

## Essential Data Flows

### Case list

#### [Updating Add-ons Use Case](#use-case-1)

#### [ Parental Controls Use Case](#use-case-2)

#### [Personal Video Recorder (PVR) Use Case](#use-case-3)

#### [Third-Party Add-ons Use Case](#use-case-4)

#### [Creating a Playlist Use Case](#use-case-5)

### Use Case 1

#### Add-on Use Case

Bob the user needs to get updates for Add-ons setup in the [Kodi Add-on Manager](https://kodi.wiki/view/Add-on_manager). Bob can set updates to occur automatically or set for manual updates for Add-ons. Bob is very busy and doesn't care as long as he doesn't have to do the updating. The updates have been set to occur automatically in the Add-on Manager. It took Bob two weekends to get Kodi set up and running and he feels accomplished in getting that done and if the sytem can manage itself he is more than happy to let it. The updates will occur every day if needed with Add-ons for Kodi. Bob is more than happy to have this removed from his plate. 

#### Updating Add-ons

* What can a user expect from getting the Add-ons updated frequently?
  * User data is protected with patches to the code.
  * Add-ons from Kodi are legitimate and operate as expected.
  * Add-ons will be supported by using the Add-on Manager.
  * The ease of use with the updated Add-ons.
  
#### Add-on Misuse Case

* Jack has a vast IT Knowledge and he knows Kodi very well.
  
  * Misuse case relating to use case 1 and diagram
  <img width="1118" alt="Screen Shot 2019-09-22 at 4 38 41 PM" src="https://user-images.githubusercontent.com/22432070/65455555-159c0b80-de0d-11e9-9b3c-0fbae5f448e4.png">

#### Prevention/Security Requirement

*insert diagram*

#### [Return to top](#case-list)

### Use Case 2

#### Parental Controls Use Case

Cheryl is a parent with Kodi. She uses such add-ons on Kodi that may have content not suitable for children, such as Adult Swim or Crackle. Cheryl does not want her child to view this content.

Cheryl would want to look at two features of Kodi: Profiles and Master Lock. Profiles are used to let multiple users of Kodi save their settings as a profile. Certain access to folders or other similar content can be customized based on the profile. To change access permissions, Master Lock is used. 
Master Lock is a standard setting on Kodi to allow users to set up a numeric password (PIN), gamepad button combo (if using game controller), or a full-text password to lock various areas in order to protect their content and settings. Three attempts are allowed to enter the pre-set password; after the third attempt, Kodi requires a restart before trying again. Under the lock preferences in Kodi, certain areas can be locked such as Videos, Pictures and Settings. It can also be set up to ask for the password when starting Kodi.

Cheryl takes her time to set up a profile for her child with a 4-digit PIN master lock code. She also sets Kodi up to ask for the PIN at startup so her child may not access her own profile for restricted content.

#### Parental Controls Misuse Case

Caleb is Cheryl's son. He is a curious 12-year-old boy. Caleb wants to use add-ons like Adult Swim or Crackle to view more mature content without his mom knowing. To bypass the PIN on Kodi against his mom's wishes, he tries to brute-force the PIN and use every 4-digit combination that makes sense to him. He uses birth years, watches his mom enter her card PIN at the grocery store, whatever he can. Kodi, by default, allows for three attempts at the lock code and then requires a restart to try again. To skip this, Caleb finds out he can edit the max number of tries in the guisettings.xml document associated with Kodi. He changes the 3 to a 9999999 and continues to try and brute force the attack. 

#### Prevention/Security Requirement

To prevent this misuse case, Kodi could add a feature to the Master Lock settings to have the PIN number expire or give a reminder to the master user to reset the PIN number. Resetting the PIN number frequently and reminding the master user to do so can be a good recommendation. At this time, however, Kodi has no way to set up PIN expirations or reminders. 

#### Misuse Case Evolved

Caleb learns that he can access the profiles.xml document associated with the Kodi installation. This document holds an MD5 hash of the PIN code between tags labeled "lockcode". Caleb could easily copy this hash and search online for a tool to reverse hashes. This way he can figure out the PIN code to accept mature content.

#### Prevention/Security Requirement

To prevent this issue, Kodi would need to either use less obvious tags or encrypt the profiles.xml document so that only a master user can access the file. At this time, Kodi makes the file easy to find and easy to read for any user. 

#### Diagram 

![Parental Controls Use Case Diagram](https://i.imgur.com/6Hk5Lnq.png)

#### [Return to top](#case-list)

### Use Case 3

#### Personal Video Recorder (PVR) Use Case

*Note: For more details on the PVR setup, refer to the "How to Guide" link under Documentation Sources below.*

Daniel has a TV antenna and a TV tuner in his Windows machine. This Windows machine also have Kodi installed. Daniel wants to use Kodi with his antenna to record live television with Kodi's PVR capabilities. Kodi on its own is not able to watch live TV and requires backend software to decode broadcast signals from Daniel's antenna. To accomplish this, Kodi relies on network-attached TV tuners or external third-party TV-tuning software to provide a video stream. This acts as the PVR backend. The PVR backend will then work with a PVR client add-on as middleware with Kodi. Daniel decides to use [NextPVR](https://kodi.wiki/view/NextPVR) as the backend software. Daniel updates and configures NextPVR to the latest version, identifying his antenna. NextPVR will use the antenna to look for different tuners (ATSC is the most used in US), and scan for channels. Within the setup, Daniel selects the Windows folder to hold recordings. NextPVR's default is under C:\Temp. Daniel integrates NextPVR on Kodi and enables Live TV in Kodi's main settings. Kodi itself only acts as a graphical interface to the PVR software. 

#### Personal Video Recorder (PVR) Misuse Case

Sandra is Daniel's irritated neighbor. Daniel has habitually had his buddies over to watch this football games going on every Saturday. His buddies take up a bunch of parking spaces and just cause a ruckus overall. Daniel tries to be a friendly neighbor however, and tries to tell Sandra that he and his friends are just having a fun time. Daniel brags about Kodi's PVR capabilities and antenna setup to Sandra. He saves money to not need cable but is able to receive signal for the games. Sandra has a technical background and wants some peace and quiet. She looks into Kodi and what PVR add-ons Kodi typically uses. The location of her house is close enough to Daniel's that she can watch his open network traffic. Sandra assumes he leaves it open so his buddies can use his WiFi when they come over. Kodi only uses HTTP when updating add-ons. Sandra decides to wait for the right time and commit a MiTM attack when the add-on Daniel uses, NextPVR, has an update available. She inserts a malicious payload to simply run an error on the add-on when opened, stating that services were not available at that time. Daniel and his buddies try messing with the antenna and changing settings on his Kodi hosting machine, but can't get it to work. Daniel and his buddies decide to go to another buddy's house to watch the game until the issue is resolved. Sandra gets at least a few weekends to herself before another update comes out for NextPVR.

#### Prevention/Security Requirement

The best way to prevent this misuse case would be to update the add-on via HTTPS. At this time, Kodi only requires add-ons to be from an HTTP server repository and thus does not meet this security requirement. 

#### Diagram

![PVR Use Case Diagram](https://i.imgur.com/0jgf9Mv.png)

#### [Return to top](#case-list)

### Use Case 4

#### Third-Party Add-ons Use Case

Dan is a user of Kodi and has numerous add-ons already installed on his device. He sees a third-party add-on that he would like to put onto Kodi. He has used third party add-ons before and has had no issues.  While the third-party add-ons are not officially Kodi approved add-ons, they are still maintained by the community and Kodi allows them to be used.

#### Third-Party Add-ons Misuse case

Jake is a hacker who likes to steal people’s personal information to use for his own malicious needs as well as sell the information to others. The buyers and Jake can then use the information to steal someone’s identity.  By doing this he can make a lot of money to buy the new car he has always wanted. Since Jake is well versed in placing hidden backdoors into code that are easily missed, he decides he is going to go to a third-party add-on and start to contribute in the community. Some of his code gets accepted for the add-on, including the hidden backdoor, which happens to be the same add-on Dan has just downloaded. Due to Dan having the third-party add-on with the backdoor, Jake can access Dan’s files from his computer where he has Kodi installed.

#### Prevention/Security Requirement

*Then insert diagram*

#### [Return to top](#case-list)

### Use Case 5

#### Creating a Playlist Use Case

Kari is a user of Kodi, and has it installed on numerous devices such as her computer. Kari would like to set up a playlist for her favorite shows. She is wanting the TV show playlist set up so the next episode will automatically start playing after the previous one finishes.  ** i elaborate more on set up**

#### Creating a Playlist Misuse Case

Alex is a hacker who has found a persistent XSS vulnerability in Kodi’s web interface that allows arbitrary HTML/script code execution to be implemented in the victim’s browser when creating a new playlist. Kari is in her account now and wants to set up her new playlist for the TV shows she is watching.  She logs in and goes to where she can create a new playlist.  She clicks ‘New Playlist’ button that will allow her to create her personalized list. When she clicks the button there is an alert that says “An unexpected error occurred. Please try logging back in.” and is redirected back to the login page. Now that the code has been executed, Alex is able to hijack Kari’s session by stealing the new session cookie and bypass authentication to get into her account.

* diagram
* Use case 5 security requirements/prevention of whatever it is

#### [Return to top](#case-list)

## Observation of Security-Related Configuration and Installation Issues

(Insert intro paragraph??) - Anna

Users can browse all of Kodi's Official Add-ons on their [website](https://kodi.tv/addons). An issue that has occurred frequently is the lack of a working source link. Numerous Add-ons will include source code links. Not all Add-ons on Kodi's page included a link to the source code. For example, Kodi offers a [Food Network](https://kodi.tv/addon/plugins-video-add-ons/food-network) Add-on. The Add-on appears to be working with it's last update in January of 2019. However, clicking the link for the source code behind the Add-on, a GitHub 404-page displays. Food Network was not a special case. The same situation occurred when looking at the source code for Add-ons such as [ABC Family](https://kodi.tv/addon/plugins-video-add-ons/abc-family), [Travel Channel](https://kodi.tv/addon/plugins-video-add-ons/travel-channel), [HGTV](https://kodi.tv/addon/plugins-video-add-ons/hgtv), and [GQ Magazine](https://kodi.tv/addon/plugins-video-add-ons/gq).

Earlier a case use was presented surrounding Master Lock and a PIN password. Masterlock does give the option for using a full-text password or gamepad button combo, but Kodi's official [Wiki](https://kodi.wiki/view/Settings/Interface/Master_lock) primarily talks about the PIN code setup. The case also mentioned how easy it is to find the lockcode via their unencrypted XML files. Simply Google Searching "kodi forgot master pin" and checking the first search result takes the user to an official Kodi support [thread](https://forum.kodi.tv/showthread.php?tid=224101). The thread presents right away in the profiles.xml document, there is an MD5 hash of the lockcode between tags labeled "lockcode". A user could easily revert the hash to its lock code or delete the hash line to dispose of the lock code entirely. Scrolling down on this thread, it is mentioned within the guisettings.xml document has an easy to understand set of "masterlock" tags that contain the line for the max number of tries allowed. It is very simple to change and could go unnoticed. 

*3rd party add-on community support but Kodi not responsible for any  - Anna* 

*Paragraph about add-on checker Kodi utilizes - Marvin*

#### [Return to top](#case-list)

## GitHub Link

* Put in GitHub repo showing internal project task assignments and collaborations in finishing. - Anna

## Documentation Sources

* Kodi [Profiles](https://kodi.wiki/view/Profiles)
* Kodi [Master Lock](https://kodi.wiki/view/Settings/Interface/Master_lock)
* [PVR Information](https://kodi.wiki/view/PVR_FAQ)
* [How to Guide](https://www.howtogeek.com/247311/how-to-watch-live-tv-on-your-kodi-media-center-with-nextpvr/) for watching Live TV on Kodi (linked from Kodi's Wiki page)
* [PVR Recording Software](https://kodi.wiki/view/PVR_recording_software)

#### [Return to top](#case-list)


