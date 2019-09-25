# Requirements for Software Security Engineering

## Essential Data Flows

![Kodi data flows](https://user-images.githubusercontent.com/22432070/65477501-1c963e80-de4c-11e9-9410-f9e9362682ba.PNG)

## Case list

#### [Case 1](#use-case-1): Updating Add-ons Use Case.

#### [Case 2](#use-case-2): Parental Controls Use Case

#### [Case 3](#use-case-3): Personal Video Recorder (PVR) Use Case

#### [Case 4](#use-case-4):

#### [Case 5](#use-case-5):

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

Caleb is Chery's son. He is a curious 12-year-old boy. Caleb wants to use apps like Adult Swim or Crackle to view more mature content without his mom knowing. To bypass the PIN on Kodi against his mom's wishes, he tries to brute-force the PIN and use every 4-digit combination that makes sense to him. He uses birth years, watches his mom enter her card PIN at the grocery store, whatever he can. He tries all the combinations on Kodi and restarts every three attempts as required of the software.

If Caleb does find the PIN, he can sneakily view mature content when his mom isn't home on the Kodi software.

#### Prevention/Security Requirement

To prevent this misuse case, Kodi could add a feature to the Master Lock settings to have the PIN number expire or give a reminder to the master user to reset the PIN number. Resetting the PIN number frequently and reminding the master user to do so can be a good recommendation.

![Parental Controls Use Case Diagram](https://i.imgur.com/vXsFsuX.png)

#### [Return to top](#case-list)

### Use Case 3

#### Personal Video Recorder (PVR) Use Case

*Note: For more details on the PVR setup, refer to the "How to Guide" link under Documentation Sources below.*

Daniel has a TV antenna and a TV tuner in his Windows machine. This Windows machine also have Kodi installed. Daniel wants to use Kodi with his antenna to record live television with Kodi's PVR capabilities. Kodi on its own is not able to watch live TV and requires backend software to decode broadcast signals from Daniel's antenna. To accomplish this, Kodi relies on network-attached TV tuners or external third-party TV-tuning software to provide a video stream. This acts as the PVR backend. The PVR backend will then work with a PVR client add-on as middleware with Kodi. Daniel decides to use [NextPVR](https://kodi.wiki/view/NextPVR) as the backend software. Daniel updates and configures NextPVR to the latest version, identifying his antenna. NextPVR will use the antenna to look for different tuners (ATSC is the most used in US), and scan for channels. Within the setup, Daniel selects the Windows folder to hold recordings. NextPVR's default is under C:\Temp. Daniel integrates NextPVR on Kodi and enables Live TV in Kodi's main settings. Kodi itself only acts as a graphical interface to the PVR software. 

#### Personal Video Recorder (PVR) Misuse Case

Jerry the son of Daniel and is a young adult with a lot of free time. He uses his freetime to learn about computer networking and its vulnerabilities. He recently learned what Man-in-the-Middle (MiTM) attacks were and wanted to try one out for himself. He finds out Kodi only uses HTTP when updating its add-ons and decides to try to enact a MiTM attack. He goes into Kodi's settings and turns off automatic updates for add-ons so he can wait for the next update for NextPVR and launch his attack then. For practice, he occasionally looks for updates for other add-ons and inserts himself between the communications during the update to get an idea how communications work. After a few weeks, he notices an update available for NextPVR. Again, he inserts himself between the Kodi machine and the add-on server, gets the update details from the server, inserts a malicious payload, and sends it back to the Kodi machine.

#### Prevention/Security Requirement

*Then insert diagram*

#### [Return to top](#case-list)

### Use Case 4

#### Third party add-ons Use Case

#### Third party add-ons Misuse case

#### Prevention/Security Requirement

*Then insert diagram*

#### [Return to top](#case-list)

### Use Case 5

#### Creating Playlist Use Case

Kari is a user of Kodi and has it installed on numerous devices such as her computer. Kari would like to set up a playlist for her favorite shows. She is wanting the TV show playlist set up so the next episode will automatically start playing after the previous one finishes.  ** i elaborate more on set up**

#### Creating Playlist Misuse Case

Alex is a hacker who has found a persistent XSS vulnerability in Kodi’s web interface that allows arbitrary HTML/script code execution to be implemented in the victim’s browser when creating a new playlist. Kari is in her account now and wants to set up her new playlist for the TV shows she is watching.  She logs in and goes to where she can create a new playlist.  She clicks ‘New Playlist’ button that will allow her to create her personalized list. When she clicks the button there is an alert that says “An unexpected error occurred. Please try logging back in.” and is redirected back to the login page. Now that the code has been executed, Alex is able to hijack Kari’s session by stealing the new session cookie and bypass authentication to get into her account.

* diagram
* Use case 5 security requirements/prevention of whatever it is

#### [Return to top](#case-list)

## Observation of Security-Related Configuration and Installation Issues

(Insert intro paragraph??)

Users can browse all of Kodi's Official Add-ons on their [website](https://kodi.tv/addons). An issue that has occurred frequently is the lack of a working source link. Numerous Add-ons will include source code links. Not all Add-ons on Kodi's page included a link to the source code. For example, Kodi offers a [Food Network](https://kodi.tv/addon/plugins-video-add-ons/food-network) Add-on. The Add-on appears to be working with it's last update in January of 2019. However, clicking the link for the source code behind the Add-on, a GitHub 404 page displays. Food Network was not a special case. The same situation occurred when looking at the source code for Add-ons such as [ABC Family](https://kodi.tv/addon/plugins-video-add-ons/abc-family), [Travel Channel](https://kodi.tv/addon/plugins-video-add-ons/travel-channel), [HGTV](https://kodi.tv/addon/plugins-video-add-ons/hgtv), and [GQ Magazine](https://kodi.tv/addon/plugins-video-add-ons/gq).

*lockcode in xml (profiles?) and can delete the line for lockcode*

*3rd party add-on community support but Kodi not responsible for any repurcussions* 

*Paragraph on banned add-ons*

*Paragraph about add-on checker Kodi utilizes*

## GitHub Link

* Put in GitHub repo showing internal project task assignments and collaborations in finishing.

## Documentation Sources

* Kodi [Profiles](https://kodi.wiki/view/Profiles)
* Kodi [Master Lock](https://kodi.wiki/view/Settings/Interface/Master_lock)
* [PVR Information](https://kodi.wiki/view/PVR_FAQ)
* [How to Guide](https://www.howtogeek.com/247311/how-to-watch-live-tv-on-your-kodi-media-center-with-nextpvr/) for watching Live TV on Kodi (linked from Kodi's Wiki page)
* [PVR Recording Software](https://kodi.wiki/view/PVR_recording_software)

#### [Return to top](#case-list)
