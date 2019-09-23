# Requirements for Software Security Engineering

## Essential Data Flows

### Use Case 1

* Use Case 
<img width="1118" alt="Screen Shot 2019-09-22 at 4 38 41 PM" src="https://user-images.githubusercontent.com/22432070/65455555-159c0b80-de0d-11e9-9b3c-0fbae5f448e4.png"> 

(use case with actor)
* What can a user expect from add-ons?
  * User data is protected
  * Add-ons from Kodi are legitimate and operate as expected.
  * Add-ons should be supported
  * Misuse case relating to use case 1 and diagram

#### Updating Add-ons

#### Add-on Use Case

(Use case relating to HTTP)

#### Add-on Misuse Case

(Misuse case relating to HTTP)

#### Prevention/Security Requirement

Fill in some stuff

*insert diagram*

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

*Insert diagram*

### Use Case 3

#### Personal Video Recorder (PVR) Use Case

*Note: For more details on the PVR setup, refer to the "How to Guide" link under Documentation Sources below.*

Daniel has a TV antenna and a TV tuner in his Windows machine. This Windows machine also have Kodi installed. Daniel wants to use Kodi with his antenna to record live television with Kodi's PVR capabilities. Kodi on its own is not able to watch live TV and requires backend software to decode broadcast signals from Daniel's antenna. Daniel decides to use [NextPVR](https://kodi.wiki/view/NextPVR) as the backend software. This software is an official add-on from Kodi and comes preinstalled. Daniel updates and configures NextPVR to the latest version, identifying his antenna. NextPVR will use the antenna to look for different tuners (ATSC is the most used in US), and scan for channels. Within the setup, Daniel selects the Windows folder to hold recordings. NextPVR's default is under C:\Temp. Daniel integrates NextPVR on Kodi and enables Live TV in Kodi's main settings.

### Personal Video Recorder (PVR) Misuse Case

*Something about ISP Spoofing?*

### Prevention/Security Requirement

*Then insert diagram*

### Use Case 4

#### Third party add-ons Use Case

#### Third party add-ons Misuse case

#### Prevention/Security Requirement

*Then insert diagram*

### Use Case 5: (Label?)

* Use case 5 description and diagram
* Misuse case relating to use case 5 and diagram
* Use case 5 security requirements/prevention of whatever it is

## Observation of Security-Related Configuration and Installation Issues

*Insert paragraph about some official add-ons githubs links from wiki page lead to 404*

*Insert paragraph about copyright and Kodi*

*Paragraph about add-on checker Kodi utilizes*

## GitHub Link

* Put in GitHub repo showing internal project task assignments and collaborations in finishing. 

## Documentation Sources

* Kodi [Profiles](https://kodi.wiki/view/Profiles)
* Kodi [Master Lock](https://kodi.wiki/view/Settings/Interface/Master_lock)
* [PVR Information](https://kodi.wiki/view/PVR_FAQ)
* [How to Guide](https://www.howtogeek.com/247311/how-to-watch-live-tv-on-your-kodi-media-center-with-nextpvr/) for watching Live TV on Kodi (linked from Kodi's Wiki page)
