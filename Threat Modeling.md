# Design for Software Security Engineering

### Add-ons Model Level 0

![Level0](https://user-images.githubusercontent.com/22432070/68550453-851f8780-03c8-11ea-9476-a4bdcedc3f46.PNG)

### Add-ons Model Level 1

![level1](https://user-images.githubusercontent.com/22432070/68550382-f6126f80-03c7-11ea-90bf-256612c9cd79.PNG)

[Add-on Report](https://github.com/mroejr/BAAM/blob/master/Ann-on%20report.pdf)

### PVR Model Level 0

![2ndlevel0](https://user-images.githubusercontent.com/22432070/68342750-dff76d00-00b0-11ea-9323-2ccccdb8e34e.PNG)

### PVR Model Level 1

![2ndlevel1](https://user-images.githubusercontent.com/22432070/68550390-032f5e80-03c8-11ea-8c9e-0d414624e536.PNG)

[PVR Report](https://github.com/mroejr/BAAM/blob/master/PVR.pdf)

### Parental Controls Model Level 0

![Parental Controls Lvl 0 Diagram](https://i.imgur.com/5defJBx.png)


### Parental Controls Model Level 1

![Parental Controls Lvl 1 Diagram](https://i.imgur.com/tIOLRsh.png)

[Parental Controls Report](https://github.com/mroejr/BAAM/blob/master/Parental%20Controls.pdf)

### Creating Playlists Model Level 0

![Create Playlist Lvl 0 Diagram](https://i.imgur.com/dMpqTbD.png)
 

### Creating Playlists Model Level 1

![Create Playlist Lvl 1 Diagram](https://i.imgur.com/oOT1Nu4.png)  

[Create Playlist Report](https://github.com/mroejr/BAAM/blob/master/Threat%20Modeling%20Create%20Playlist%20Report.pdf)

## Summary of Observations

We evaluated the threats generated from Microsoft's TMT software. Below are our findings after reviewing Kodi Wiki documentation.

--------------------------

### Spoofing

### Tampering

### Repudiation

### Information Disclosure

### Denial of Service

In the scope of potential Denial of Service attacks, when it comes to the hardware Kodi is installed on, that is outside the scope of Kodi. When it comes to the software itself, it depends on what features of Kodi are being used. If a user of the software primarily uses locally-stored media, there is little possibility of a DoS attack to happen to prevent the user from consuming such media. However, Kodi does offer a Webserver feature to allow users to access content through a web interface over HTTP, port 80. This <i>could</i> potentially be suspceptible to a DoS attack, but because this is typically a home-use software, it can be argued that the risk is accepted.

[Howver stuff about Kodi installed hardware being used for DoS or DDoS attacks?]

### Elevation of Privilege

Within Kodi in the context of profiles, an administrative user can set up different profiles for other users to customize their Kodi experience. This also gives the option of restricting access to certain media, add-ons, etc. to different users. This could include reasons such as Parental Controls. When restricting access, the only way a restricted user profile can access restricted content is to use the Master Lock PIN. The PIN is created by the administrative user and then MD5 hashed and stored in the guisettings.xml file of the local storage Kodi is installed on. Kodi does not offer anymore security than the hash and the xml file is not encrypted. Thus, if a user has access to the local filesystem, they could recover the MD5 hashed PIN and figure it out, allowing the would-be restricted content to be accessed by the user profile. For recommendations in this scope for what Kodi could do to prevent this, perhaps the guisettings.xml and other similar XML files should be hidden or encrypted by default in the local filesystem. They could also keep a log of when the Master Lock PIN was used in the software for the administrative user to check at any time. 

--------------------------

### Link to Repo

[GitHub Repo Link](https://github.com/mroejr/BAAM/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Design+for+SSE%22)

### Reflection

Over the course of the semester, it seems the group has improved in communicating with each other. It has become easier to delegate tasks equally to other members of the group for project deliverables. As with previous deliverables, individual taks were created and split among the group members, but this time around we bounced around different ideas and input with one another. Hopefully we can produce better quality deliverables for the rest of the semester because of this.
