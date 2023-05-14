After a Fress Install Boot Up with recovary mode and after thet Chenge the Network Repositories to Cloudflare  
```base
kali-tweaks
```
Make a full upgrade by this Commands

```bash
sudo apt update && sudo apt full-upgrade -y
```

Then Reboot the system

```bash
sudo reboot
```
After start the machine run this command to remove the unwanted programs

```bash
sudo apt remove parole*
```

Now add some important Program's Repositories in the sources.list using this commands

Proton VPN:

```bash
cd /home/lucifer/Downloads && wget https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.3_all.deb && sudo dpkg -i protonvpn-stable-release_1.0.3_all.deb && rm protonvpn-stable-release_1.0.3_all.deb
```

Docker-ce:

```bash
printf '%s\n' "deb https://download.docker.com/linux/debian bullseye stable" | sudo tee /etc/apt/sources.list.d/docker-ce.list && curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-ce-archive-keyring.gpg
```

VirtualBox:

```bash
curl -fsSL https://www.virtualbox.org/download/oracle_vbox_2016.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/oracle_vbox_2016.gpg && curl -fsSL https://www.virtualbox.org/download/oracle_vbox.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/oracle_vbox.gpg && echo "deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bullseye contrib" | sudo tee /etc/apt/sources.list.d/virtualbox.list
```

Install All Required Applications:

```bash
sudo apt update && sudo apt install -y net-tools fonts-indic conky-all curl jq moc vlc libu2f-udev gcc g++ python3-pip python2 snapd burpsuite ffmpeg libavdevice59 docker-ce docker-ce-cli containerd.io mugshot bleachbit john metasploit-framework dirbuster nmap nikto hashid libimage-exiftool-perl binwalk steghide wordlists gobuster protonvpn xsltproc exploitdb hydra gufw transmission dkms virtualbox virtualbox-ext-pack
```

Download Required applications deb files from official sources and install them [Chrome, VS Code, XDM]:

```bash
cd /home/lucifer/Downloads && wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb && wget https://az764295.vo.msecnd.net/stable/b3e4e68a0bc097f0ae7907b217c1119af9e03435/code_1.78.2-1683731010_amd64.deb && wget https://github.com/subhra74/xdm/releases/download/8.0.26/xdman_gtk_8.0.26_amd64.deb && wget https://github.com/RickdeJager/stegseek/releases/download/v0.6/stegseek_0.6-1.deb && sudo dpkg -i *
```

Install haiti:

```bash
sudo gem install haiti-hash
```

Start All Importaint Services:

```bash
sudo systemctl start bluetooth.service && sudo systemctl start snapd.aa-prompt-listener.service && sudo systemctl start snapd.apparmor.service && sudo systemctl start snapd.recovery-chooser-trigger.service && sudo systemctl start snapd.seeded.service && sudo systemctl start snapd.service && sudo systemctl start snapd.socket
```

Enable All Importaint Services:

```bash
sudo systemctl enable bluetooth.service && sudo systemctl enable snapd.aa-prompt-listener.service && sudo systemctl enable snapd.apparmor.service && sudo systemctl enable snapd.recovery-chooser-trigger.service && sudo systemctl enable snapd.seeded.service && sudo systemctl enable snapd.service && sudo systemctl enable snapd.socket
```

Install Setup Spotify:

```bash
sudo snap refresh && sudo snap install spotify
```
Then Copy the Desktop Entry:

```bash
sudo cp /var/lib/snapd/desktop/applications/spotify_spotify.desktop /usr/share/applications/
```

Install the pip for python2:

```bash
cd /home/lucifer/Downloads && wget https://bootstrap.pypa.io/pip/2.7/get-pip.py && python2 get-pip.py
```

Add Snap & pip Path in to the PATH:

```bash
# Add Directory into the PATH
export PATH="/home/lucifer/.local/bin:/snap/bin:$PATH"
```

Add this Entry in the .zshrc & .bashrc for the user and the root:

User .zshrc & .bashrc:

```bash
nano /home/lucifer/.zshrc
```
```bash
nano /home/lucifer/.bashrc
```

Root .zshrc & .bashrc:

```bash
sudo nano /root/.zshrc
```
```bash
sudo nano /root/.bashrc
```

Install Telegram:

```bash
cd /home/lucifer/Downloads && wget https://updates.tdesktop.com/tlinux/tsetup.4.8.1.tar.xz && tar -xf tsetup.4.8.1.tar.xz && mkdir /home/lucifer/opt && mv /home/lucifer/Downloads/Telegram /home/lucifer/opt && cd /home/lucifer/opt/Telegram && ./Telegram
```

Settings The <b>lightdm.conf</b> to show username in login screen:

```bash
sudo nano /etc/lightdm/lightdm.conf
```

Then Uncomment the <b>greeter-hide-users=false</b>, <b>user-session=lucifer</b>  
Chenge the user-session to your User Name [In my case it is <i>lucifer</i>]

Chenge the Swappiness value:

```bash
sudo nano /etc/sysctl.conf
```
Then write the line in end of the file:

```bash
vm.swappiness=10
```
Then save this with Ctrl + O and Ctrl + X

Then Use the <b>noatime</b> in the <b>fstab</b>

```bash
sudo nano /etc/fstab
```

Write the <i>noatime,</i> before <i>errors=remount-ro</i>

Install all the Browser Extentions & theme:

```txt
Flagfox, FoxyProxy Standard, Wappalyzer, Dark Reader, Splatoon 2 Colours [Theme]
```

At last Install Extentions for VS Code:

```txt
C/C++, CMake Tools, Extension Pack for Java, Live Server, Markdown All in One, Prettier - Code formatter, Python, Pylance
```