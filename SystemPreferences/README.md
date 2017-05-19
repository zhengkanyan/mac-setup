# System Preferences

First thing you need to do, on any OS actually, is update the system! For that: **Apple menu \(\) &gt; About This Mac &gt; Software Update.**

Also upgrade your OS in case you want to work on the latest OS. Sierra is a free upgrade so please check that.

If this is a new computer, there are a couple tweaks you would like to make to the System Preferences. Feel free to follow these, or to ignore them, depending on your personal preferences.

### Users & Groups

* Set up Password, Apple ID, Picture, etc.

### Trackpad &lt;do not know if I need it&gt;

* Point & Click
  * Enable Tap to click with one finger
  * Change Secondary click to right corner
  * Uncheck three finger drag
* Scroll & Zoom
  * Uncheck all apart from Zoom in and out

### Dock

* Visual settings
  * Change position to left and make the size of Icons small
* Other settings

  * Remove workspace auto-switching

    ```
      $ defaults write com.apple.dock workspaces-auto-swoosh -bool NO
      $ killall Dock
    ```

### Finder

Although Finder sucks, I have to use it since there are no total commander on macOS T.T

* Toolbar
  * Update to add path, new folder and delete
* Sidebar
  * Add home and code directory
  * Remove shared and tags
  * New finder window to open in the home directory \(in "general" tab\)

### Menubar

* Remove the display and Bluetooth icons \(may need to show if use bluetooth devices\)
* Change battery to show percentage symbols

### Spotlight

* Uncheck fonts, images, files etc.
* Uncheck the keyboard shortcuts as we'll be replacing them with Alfred.

### Accounts

* Add an iCloud account and sync Calendar, Find my mac, Contacts etc.

### Write to NTFS on OSX Yosemite and El Capitan

ntfs-3g is way too slow, I will use a commercial mount software if need to.

Instead, format my all portable storage devices to ExFat.

Actually, there are some mistakes below

#### Install Homebrew and Homebrew Cask

* Instructions [here](http://sourabhbajaj.com/mac-setup/Homebrew/README.html)!

#### Update Homebrew formulae:

```
$ brew update
```

#### Install osxfuse

* If you are on OSX 10.11 \(El Capitan\), install the \(3.x.x\) from [https://github.com/osxfuse/osxfuse/releases](https://github.com/osxfuse/osxfuse/releases).

  $ brew cask install osxfuse

#### Install ntfs-3g

```
$ brew install homebrew/fuse/ntfs-3g
```

#### If you are on OSX 10.11 \(El Capitan\), temporary disable System Integrity Protection.

* **reboot** and hold CMD+R to get in recovery mode
* Open the terminal and type

```
$ csrutil disable
```

* **reboot** normally

#### Create a symlink for mount\_ntfs

```
$ sudo mv /sbin/mount_ntfs /sbin/mount_ntfs.original
$ sudo ln -s /usr/local/sbin/mount_ntfs /sbin/mount_ntfs
```

#### If you are on OSX 10.11 \(El Capitan\), re-enable System Integrity Protection.

* **reboot** and hold CMD+R to get in recovery mode
* Open the terminal and type

```
$ csrutil enable
```

* **reboot** normally



