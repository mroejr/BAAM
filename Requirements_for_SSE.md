# Requirements for Software Security Engineering

## Essential Data Flows

(some description)

### Use Case 1: Add-ons

Add-ons are free pieces of software Kodi offers on its main software. Add-ons can be related to Audio or Video to stream internet content, skins to change the interface, etc. Add-ons update automatically as new versions are released. 
* Use Case

(use case with actor)

  * What can a user expect from add-ons?
    * User data is protected
    * Add-ons from Kodi are legitimate and operate as expected. 
    * Add-ons should be supported
* Misuse case relating to use case 1 and diagram
* Security requirements for Add-Ons
  * 

### Use Case 2:

#### Parental Controls Use Case

Cheryl is a parent with Kodi. She uses such add-ons on Kodi that may have content not suitable for children, such as Adult Swim or Crackle. Cheryl does not want her child to view this content.

Cheryl would want to look at two features of Kodi: Profiles and Master Lock. Profiles are used to let multiple users of Kodi save their settings as a profile. Certain access to folders or other similar content can be customized based on the profile. To change access permissions, Master Lock is used. 
Master Lock is a standard setting on Kodi to allow users to set up a numeric password (PIN), gamepad button combo (if using game controller), or a full-text password to lock various areas in order to protect their content and settings. Three attempts are allowed to enter the pre-set password; after the third attempt, Kodi requires a restart before trying again. Under the lock preferences in Kodi, certain areas can be locked such as Videos, Pictures and Settings. It can also be set up to ask for the password when starting Kodi. 

Cheryl takes her time to set up a profile for her child with a 4-digit PIN master lock code. She also sets Kodi up to ask for the PIN at startup so her child may not access her own profile for restricted content. 

#### Misuse Case: Parental Controls

Caleb is Chery's son. He is a curious 12 year old boy. Caleb wants to use apps like Adult Swim or Crackle to view more mature content without his mom knowing. To bypass the PIN on Kodi against his mom's wishes, he tries to brute-force the PIN and use every 4-digit combination that makes sense to him. He uses birth years, watches his mom enter her card PIN at the grocery store, whatever he can. He tries all the combinations on Kodi, and restarts every three attempts as required of the software. 

If Caleb does find the PIN, he can sneakily view mature content when his mom isn't home on the Kodi software. 

#### Prevention/Security Requirement

To prevent this misuse case, Kodi could add a feature to the Master Lock settings to have the PIN number expire or give a reminder to the master user to reset the PIN number. Resetting the PIN number frequently and reminding the master user to do so can be a good recommendation. 

#### Diagram

(Insert diagram of use and misuse case w/parental controls)

### Use Case 3: (Label?)

* Use case 3 description and diagram
* Misuse case relating to use case 3 and diagram
* Use case 3 security requirements/prevention of whatever it is

### Use Case 4: (Label?)

* Use case 4 description and diagram
* Misuse case relating to use case 4 and diagram
* Use case 4 security requirements/prevention of whatever it is

### Use Case 5: (Label?)

* Use case 5 description and diagram
* Misuse case relating to use case 5 and diagram
* Use case 5 security requirements/prevention of whatever it is


## Observation of Security-Related Configuration and Installation Issues

* Review OSS project documentation for security-related configuration and installation issues. Summarize your observations.


## GitHub Link
* Put in github repo showing internal project task assignments and collaborations in finishing. 

## Documentation Sources

* Kodi [Profiles](https://kodi.wiki/view/Profiles)
* Kodi [Master Lock](https://kodi.wiki/view/Settings/Interface/Master_lock)
