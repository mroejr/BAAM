# Assurance Cases

### Assurance Case List

* #### [Assurance Case 1](#assurance-case-1)

* #### [Assurance Case 2](#assurance-case-2)

* #### [Assurance Case 3](#assurance-case-3)

* #### [Kodi effectively stores & protects personal information about its users.](#assurance-case-4)

### Assurance Case 1
![User Profile Separation Diagram](https://i.imgur.com/L1QYTvM.jpg)

#### Evidence

In support for Evidence E3, for Claim C4, Kodi's [Wiki](https://kodi.wiki/view/Settings/Interface/Master_lock) shows that Master Lock can be disabled as to help prevent other users from accessing other user profiles. In looking for support of Evidence E4, Kodi Wiki nor forums display any information for the availability of 2-factor authentication, which does not help Claim C7, C5, or C1.  

In support of Evidence E2 and E1 to support Claim C6, Kodi by default does not have an auto profile-logoff option within its settings. However, Kodi does offer an Official Add-on named [Logoff](https://kodi.wiki/view/Add-on:Logoff), that makes the software automatically log off from a user profile after a user-set "screensaver time". This add-on, along with Kodi's built-in settings for showing the login screen on [startup](https://kodi.wiki/view/Settings/Profiles#General) help support Claim C2, and the top claim. 

In support of Evidence E4, when setting up user [profiles](https://kodi.wiki/view/Profiles#Specific_profile_settings) there is an option to set up locks on Media info and Media sources (e.g. Separate, Shares with Default, Shares with Default (Read Only) and Separated (Locked)). This gives Kodi users the option to share media info and/or sources if they desire to do so.

#### [Return to top](#assurance-case-list)

### Assurance Case 2
![Preventing Users from Scams Diagram](https://i.imgur.com/wRwa5dJ.jpg)

#### Evidence

In finding suitable Evidence for E3, it is found Kodi does indeed display a warning [message](https://kodi.wiki/images/thumb/c/cb/Addon_unknown_sources_1.png/500px-Addon_unknown_sources_1.png) warning users about potential damages and how it is their responsibility. This does not necessarily support the idea that Kodi prevents potential scams, but at least puts the responsibility upon the user. Because the software is open-source, Kodi cannot force its users to only install official add-ons. This would support Claims C8 and C1 and the overall Top Claim. 

In looking for support for Evidence E1, under Kodi's Repository Submission Guidelines [page](https://kodi.wiki/view/Add-on_rules) there is a listed guideline bullet point that all the files must be free and legal to distribute. Distributing any malware to gain unauthorized access to another user's macine is prohibited in most countries, including the [United States](https://www.nyccriminallawyer.com/white-collar-crimes/distribution-malicious-software/). In addition, it is stated the inclusion of the add-on to the official repo is under the sole discretion of Team Kodi. If within the vetting process, Kodi finds a submitted add-on tries to include malware or monetizes the add-on when they are not the copyright holder, they will not accept the add-on. 

For accessing Rebuttal R3, Kodi has little power in controlling what manufacturers sell for hardware pre-installed with Kodi. Kodi will refuse support to users who use [banned](https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons) add-ons from official Kodi forums, websites, IRC and social media channels controlled by Team Kodi or XBMC Foundation, however that is all they do. Kodi does not go more in depth in preventing its users from using Kodi for malicious or illegal means. Although Claim C10 can be supported, there is no evidence to refute Rebuttal R10 and thus C12 and Evidence E6 cannot be supported. 

With using [skins](https://kodi.wiki/view/Skins) in Kodi, relating to E5, no evidence could be found of Kodi stating they review files associated with available skins for download. A [manual](https://kodi.wiki/view/Skinning_Manual) and multiple [tutorials](https://kodi.wiki/view/Skinning_tutorials) are available for those wanting to create skins, however there is no evidence that there is any file checking involved. This does not support C11 or C4, and thus does not help the top claim.

In looking for support of Evidence E2, Kodi can [support](https://kodi.wiki/view/HTTP) both HTTP and HTTPS, but only requires HTTP. However, Kodi does not provide evidence to support the evidence required for Claim C7. Kodi does not explicitly state is any of its Wiki pages or forums that add-ons are updated via HTTPS instead of HTTP. This thus does not refute the rebuttal against preventing MiTM attacks and therefore also does not support the top claim.

#### [Return to top](#assurance-case-list)

### Assurance Case 3
![Preventing Users from Add-on with Pirated Content Diagram](https://i.imgur.com/x9mOGTF.png)

#### Evidence

For Evidence E1 under Claim C4 it was difficult to find any specific code relating directly to validating user input or escaping to help mitigate XSS, but a little information was able to be located regarding client side and server-side code for [randr](https://github.com/xbmc/xbmc/blob/master/xbmc-xrandr.c).

Under Claim C5 for Evidence E2 information can be found on [Kodi’s Official Forum]( https://forum.kodi.tv/showthread.php?tid=339438) page with regards to Kodi withholding support for users with banned add-ons installed. A Kodi team member states they do not tell users what they can and cannot use their Kodi application for and will not enforce policing on a “very incomplete and volatile list of banned add-ons”. Kodi simply states that the choose to NOT give tech support for users that have banned add-ons on their system.  The team member states even if they did embed it into the code people can simply remove it and create their own compilations of Kodi.

For the Evidence under E3 for Claim C2, Kodi specifically states under their [forum rules]( https://kodi.wiki/view/Official:Forum_rules) that they will close all discussions talking about or containing links to add-ons, websites or other services that violate US copyright laws and may result in getting [banned]( https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons) from the forum. However, in this same statement Kodi somewhat contradicts themselves stating that an add-on creator or original poster can provide links to websites not hosted by Kodi for further inquires and discussion. In deciphering this, it seems that users can post links to other forums that may discuss pirated content, but they cannot post links directly to the pirated content. For example, they can post a link to a different forum not hosted by Kodi, and that different forum can contain links to the pirated content which brings up Evidence E4 for Claim C6.  The evidence found for C6 does not fall in line with what was originally presumed in that Kodi would try to close non-Kodi hosted forums with pirated content that could be used on a device with Kodi.

As new add-ons containing banned content become available, Kodi may not be aware they exist.  Under Evidence E5 for Claim C3, Kodi states on its WIKI page under [Forum rules/Banned add-ons](https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons), that their list is an example as they are aware of the dynamic nature of piracy streams and it is impossible to list all of them. Users are able to report new add-ons containing pirated content, but it may not be added to the list due to how fast and often it can change.

#### [Return to top](#assurance-case-list)

### Assurance Case 4
![Assurance case 4](https://user-images.githubusercontent.com/22432070/66684073-ca705e00-ec3e-11e9-9ca5-b514b622e769.png)

#### Evidence

#### [Return to top](#assurance-case-list)

## Reflection

In our team reflection meeting we discussed how well our approaches worked for both assignments (milestones 2 & 3).  With the third assurance case milestone we did a little more group planning which helped to move along development more efficiently. 

*What issues occurred? What did you plan to change moving forward? Etc.*

## Planning and Contribution

Our repository for this deliverable can be viewed at [GitHub BAAM Project Repository](https://github.com/mroejr/BAAM/milestone/3).


