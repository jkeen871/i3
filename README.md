# I3-gaps/Bumblebee-status/j4-dmenu on Fedora 29
I3 customizations

NOTE : at this moment this repository and instructions are incomplete.  Feel free to comment and suggest.  This should be complete in the next week or so.


Install I3 Gaps:

create a new repo for i3-gaps

    sudo vim /etc/yum.repos.d/i3-gaps.repo

Paste this content into the file :

    [gregw-i3desktop]
    name=Copr repo for i3desktop owned by gregw
    baseurl=https://copr-be.cloud.fedoraproject.org/results/gregw/i3desktop/fedora-$releasever-$basearch/
    type=rpm-md
    skip_if_unavailable=True
    gpgcheck=1
    gpgkey=https://copr-be.cloud.fedoraproject.org/results/gregw/i3desktop/pubkey.gpg
    repo_gpgcheck=0
    enabled=1
    enabled_metadata=1
* Note :  I do not specifically endorse gregw's repository, but I can say it has worked for me with no issues.

Install i3-gaps

    dnf -y install i3-gaps i3-lock

This will install i3-gaps will be available at your login screen as an additional desktop environment.

Logout and log back in to get to the default i3 desktop.

To get a terminal from the default i3 desktop press [alt-enter]
***

Clone this repository to your home directory:

    cd ~
    git clone https://github.com/jkeen871/i3-config.git
    
Install additional packages and dependencies:

    dnf -y install lightdm zenity urxvt w3m w3m-img ranger network-manager-applet volumeicon xrandr arandr gnome-settings-daemon gnome-terminal xcompmgr fontawesome-fonts powerline-fonts
       pip3 install psutil netifaces
***
Install bumble-bee status:

Bumblebee status seems to work with python3+:

    dnf install python3-devel
    pip3 install psutil netifaces


***
Install J4-dmenu-desktop 

 Follow the instructions at : 
 
     https://github.com/enkore/j4-dmenu-desktop
     
 * You will have to build this package from source, I do not know of a fedora rpm for j4-dmenu-desktop.  The basic instructions are as follows:

 Clone j4-dmenu-desktop from :
 
    cd ~
    git clone https://github.com/enkore/j4-dmenu-desktop.git
    dnf install gcc cmake
    cd ~/j4-dmenu-desktop
    cmake .
    make
    make install
 
 *neomutt and email configuration instructions are available at this git.

    https://github.com/jkeen871/Mail

Copy the contents of ~/i3-config/  to ~/.config/i3/

    cp -R ~/i3-config/* ~/.config/i3/
    
    
    

