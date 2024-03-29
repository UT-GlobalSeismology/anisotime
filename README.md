# UT-GlobalSeismology/ANISOtime

![version](https://img.shields.io/badge/version-1.3.8-yellow.svg)
![release](https://img.shields.io/badge/release-Kushiro-yellow.svg)
![aLicense](https://img.shields.io/badge/license-GPL--3-blue.svg?style=flat)
![Java8](https://img.shields.io/badge/dependencies-JRE%208-brightgreen.svg) Last updated on ***5 JUN 2021***

ANISOtime is a utility package for computing travel times of seismic waves in a laterally homogeneous, transversely isotropic (TI), spherically symmetric medium. This is free software developed by researchers presently or formerly affiliated with the global seismology group of the University of Tokyo. 
Please [verify](https://java.com/en/download/installed8.jsp) that you have the Java Runtime Environment (8+) installed before you proceed further. This is required to run ANISOtime.

# USER GUIDE

The User Guide is included in the software, but it also may be viewed [here](https://github.com/UT-GlobalSeismology/anisotime/releases/download/anisotime/user_guide.pdf).   

# DOWNLOAD AND INSTALLATION

For [Windows](https://bit.ly/31CXCX5)  
For [macOS](https://bit.ly/2DbS5NH)  
For [Linux](https://bit.ly/2DbS5NH)

Please note that the program automatically updates when a new version is released. 


# GETTING STARTED
1. [Verify](https://java.com/en/download/installed8.jsp) that you have the most recent version of Java installed on your machine.
2. Download/Install:<br>
    - Windows users: Download the file "anisotime.bat" from the above link and move it to your desktop (or some other folder where you want to use it).<br>
    - macOS/Unix/Linux users: Dowload the file "anisotime" from the above link. Open the "Terminal" app, navigate to the place where the downloaded file is stored, and change the user permissions of the file by typing ```chmod +x anisotime```.
3. Launch ANISOtime:<br>
    - Windows users: click on the icon. (We are still waiting for our "code signing certificate," so you will get a warning message that the software is unverified. Please don’t worry, and authorize your machine to launch the program. Sorry for this inconvenience.)<br>
    - macOS/Unix/Linux users: in the terminal app, type ```./anisotime```. (We are still waiting for our "code signing certificate," so if you try to launch ANISOtime by directly clicking on the icon rather than through the terminal app, you may get a warning message that the software is unverified. Please don’t worry, and authorize your machine to launch the program. Sorry for this inconvenience.)
4. If you need more information download the [User Guide](https://bit.ly/3hFNUZH), or read it through the Help tab in ANISOtime after you launch it.

# INPUT MODEL FILES

Template input model files for ANISOtime can be found as below:
- Polynomial Structure mode: [miasp_aniso.poly](https://github.com/UT-GlobalSeismology/anisotime/blob/master/miasp91_aniso.poly)
- Named Discontinuity Structure mode: [miasp_aniso.nd](https://github.com/UT-GlobalSeismology/anisotime/blob/master/miasp91_aniso.nd)

# Sample Homework Problem Using ANISOtime

Using *ANISOtime*, compute the traveltimes for the isotropic PREM and anisotropic PREM models
(for example, by using Record Section Mode) and discuss the geophysical implications of the
following:
1. Triplication phases related to the positive velocity discontinuities at depths of 410 and 660 km.
2. The shadow zone related to the outer core.
3. The difference in the traveltimes between SH and pseudo-SV waves due to the anisotropic structure in
the depth range from 24.4 to 220 km.

# SOURCE CODE

The source code for ANISOtime can be downloaded [here](https://github.com/kensuke1984/Kibrary).

# CONTACT US 

Please send email to ut-globalseis@googlegroups.com using the subject line “ANISOtime Help” if you have any questions or comments. 

# Copyright

Software and documents, Copyright © 2015-2020 Kensuke Konishi, Anselme F.E. Borgeaud, Kenji Kawai and Robert J. Geller
