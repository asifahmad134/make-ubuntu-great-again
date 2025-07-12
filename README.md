# 🆕🆒🆓 Clean Ubuntu (24.04+)

# _Make Ubuntu great again!!!!!_

# 🔥🔥🔥 PURGE without loosing ubuntu-desktop

- First remove snaps either with commands or scripts of your choice,
- then purge apps as below,
- then install apps of your choice,
- at the end, either run scripts or use bleachbit to cleanup the installation

### purge snaps with these commands, step by step

```
sudo snap list
sudo snap remove --purge <snap name>
sudo apt autopurge snapd
sudo rm -Rf /var/cache/snapd/
rm -Rf ~/snap
sudo apt autoremove --purge
```

### purge these, combined (450+ MB)

```
sudo apt purge ubuntu-report apport apport-gtk brltty orca gnome-accessibility-themes fonts-noto-cjk speech-dispatcher* libpinyin* ibus* pocketsphinx* espeak* liblouis* hplip* eog
```

### Remove bunch of CUPS stuff, also printing & printer drivers (20+MB)

```
sudo apt purge 'cups*' 'foomatic*' printer-driver-brlaser* printer-driver-foo2zjs-common* printer-driver-ptouch* printer-driver-c2esp* printer-driver-min12xxw* printer-driver-sag-gdi*
```

### CLEAN remaining packages, 49MB+

```
sudo apt autoremove --purge
//or
sudo apt autopurge
```

### Remove all backgrounds (50MB+) for 25.04, default background name
```
sudo rm /usr/share/backgrounds/!("warty-final-ubuntu.png")
```
### for removing old kernels, first identify installed and then

```
dpkg --list | grep -i linux-image
sudo apt remove --purge linux-image-[version]-generic
sudo apt remove --purge linux-headers-[version]-generic
sudo apt autoremove --purge
sudo update-grub
```

# ⭐⭐⭐ INSTALLATIONS

```
sudo apt update -y && sudo apt upgrade -y
apt search <keyword>
```

## ✴️✴️✴️ necessary pacakages

```
sudo apt install amberol curl gedit gedit-plugins git gnome-shell-extension-manager gnome-tweaks gnome-calendar loupe nautilus-admin showtime transmission tree thunar lsd foliate
```

## ✳️✳️✳️ suggestions / optional pacakages

```
sudo apt install ptyxis vlc file-roller rar unrar synaptic gnome-decoder adb fastboot thunar-media-tags-plugin gh
```

## 🎴🎴🎴 Install Node.js 22.x LTS, 24.x Current

```
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo bash -
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo bash -
sudo apt install -y nodejs
// importan global packages needed for development
sudo npm install -g npm@latest npm-check-updates typescript nodemon pnpm yarn vite
```

## 🆘🆘🆘 oh-my-posh in /usr/bin

```
sudo bash -c "$(curl -s https://ohmyposh.dev/install.sh)" -- -d /usr/bin
// add this line at the end of .bashrc
eval "$(oh-my-posh init bash --config ~/jandedobbeleer.omp.json)"
// refresh bash after selection of each theme
exec bash
```

#### Description of files in oh-my-posh folder

- all are changed/moded themes in this folder, except....
- **_25-04.bashrc_**<br>
  This is default .bashrc in ubuntu 25.04
- **_omp.bashrc_**<br>
  This is default .bashrc with omp themes commented at the end
- **_Microsoft.PowerShell_profile.ps1_**<br>
  This is for windows 10/11 terminal/powershell profile in user's My Documents folder

# 🛸👽🚚 XTRADEB packages

Unofficial Ubuntu application packages maintained by xtradeb.

[xtradeb](https://launchpad.net/~xtradeb/+archive/ubuntu/apps)<br>

```
sudo add-apt-repository ppa:xtradeb/apps -y
sudo apt update
sudo apt install  yt-dlp parabolic calibre ungoogled-chromium chromium  gnucash  intellij-idea-community  pycharm-community
```

# ⚛️⚛️⚛️ Remove language locales for chrome & electron based apps (50+ MB each)

```
- google-chrome
sudo rm /opt/google/chrome/locales/!("en-GB.pak"|"en-US.pak")
- brave browser
sudo rm /opt/brave.com/brave/locales/!("en-GB.pak"|"en-US.pak")
- slack
sudo rm /usr/lib/slack/locales/!("en-GB.pak"|"en-US.pak") && sudo rm /usr/lib/slack/LICENSE /usr/lib/slack/resources/LICENSES.chromium.html
- TickTick
sudo rm /opt/TickTick/locales/!("en-GB.pak"|"en-US.pak") && sudo rm /opt/TickTick/LICENSE.electron.txt /opt/TickTick/LICENSES.chromium.html
- replit
sudo rm /usr/lib/replit/locales/!("en-GB.pak"|"en-US.pak") && sudo rm /usr/lib/replit/LICENSES.chromium.html
- vscode
sudo rm /usr/share/code/LICENSES.chromium.html /usr/share/code/resources/app/LICENSE.rtf && sudo rm /usr/share/code/locales/!("en-GB.pak"|"en-US.pak") && sudo rm -fdr /usr/share/code/resources/app/licenses
```

# 🪛📜💻 Important Scripts

#### Best all in one tool

> [ubuntu-debullshit.sh](https://github.com/polkaulfield/ubuntu-debullshit)
> Purges snaps, installs flatpaks, and restores vanilla GNOME

#### SNAP Uninstallers / Removers

> [snap-remover.sh](https://gist.github.com/lassekongo83/808b19e034c05d10ac4e3cc259808e4e)
> Completely remove snaps from Ubuntu.
>
> [unsnap](https://github.com/popey/unsnap)
> Quickly migrate from using snap packages to flatpaks

#### Cleaners

> [snap-cleaner.sh](https://github.com/sakibulalikhan/snap-cleaner)
> Free up disk space by deleting unnecessary Snap package revisions and caches.
>
> [ubuntu_cleanup.sh](https://gist.github.com/Limbicnation/6763b69ab6a406790f3b7d4b56a2f6e8)
> A comprehensive system cleanup script that safely removes unnecessary files to free up disk space (also included in this repo)

#### Miscellaneous

> **_update-all-icon-caches.sh_** This updates icons caches
