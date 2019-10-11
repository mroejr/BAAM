# Assurance Cases

### Assurance Case List

#### [Assurance Case 1](#assurance-case-1)

#### [Assurance Case 2](#assurance-case-2)

#### [Assurance Case 3](#assurance-case-3)

#### [Assurance Case 4](#assurance-case-4)

### Assurance Case 1
![User Profile Separation Diagram](https://i.imgur.com/Jo5EMYj.jpg)

#### Evidence

TODO: Alignment check

#### [Return to top](#assurance-case-list)

### Assurance Case 2
![Preventing Users from Scams Diagram](https://i.imgur.com/SaLVagS.jpg)

#### Evidence

TODO: Alignment check

#### [Return to top](#assurance-case-list)

### Assurance Case 3
![Preventing Users from Add-on with Pirated Content Diagram](https://i.imgur.com/jv5OQkq.png)

#### Evidence

For Evidence E1 under Claim C4 it was difficult to find any specific code relating directly to validating user input or escaping to help mitigate XSS but I did locate a little information regarding client side and server side code for randr https://github.com/xbmc/xbmc/blob/master/xbmc-xrandr.c

Under Claim C5 for Evidence E2 information can be found on [Kodi’s Official Forum]( https://forum.kodi.tv/showthread.php?tid=339438) page with regards to Kodi withholding support for users with banned add-ons installed. A Kodi team member states they do not tell users what they can and cannot use their Kodi application for and will not enforce policing on a “very incomplete and volatile list of banned add-ons”. Kodi simply states that the choose to NOT give tech support for users that have banned add-ons on their system.  The team member states even if they did embed it into the code people can simply remove it and create their own compilations of Kodi.

For the Evidence under E3 for Claim C2, Kodi specifically states under their [forum rules]( https://kodi.wiki/view/Official:Forum_rules) that they will close all discussions talking about or containing links to add-ons, websites or other services that violate US copyright laws and may result in getting [banned]( https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons) from the forum. However, in this same statement Kodi somewhat contradicts themselves stating that an add-on creator or original poster can provide links to websites not hosted by Kodi for further inquires and discussion. In deciphering this, it seems that users can post links to other forums that may discuss pirated content, but they cannot post links directly to the pirated content. For example, they can post a link to a different forum not hosted by Kodi, and that different forum can contain links to the pirated content which brings up Evidence E4 for Claim C6.  The evidence found for C6 does not fall in line with what was originally presumed in that Kodi would try to close non-Kodi hosted forums with pirated content that could be used on a device with Kodi.

As new add-ons containing banned content become available, Kodi may not be aware they exist.  Under Evidence E5 for Claim C3, Kodi states on its WIKI page under [Forum rules/Banned add-ons](https://kodi.wiki/view/Official:Forum_rules/Banned_add-ons), that their list is an example as they are aware of the dynamic nature of piracy streams and it is impossible to list all of them. Users are able to report new add-ons containing pirated content but it may not be added to the list due to how fast and often it can change.


#### [Return to top](#assurance-case-list)

### Assurance Case 4

#### Evidence

#### [Return to top](#assurance-case-list)

## Reflection

*What issues occurred? What did you plan to change moving forward? Etc.*

## Planning and Contribution

Our repository for this deliverable can be viewed at [GitHub BAAM Project Repository](https://github.com/mroejr/BAAM/milestone/3).
