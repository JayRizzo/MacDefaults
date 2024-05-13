# MacDefaults
Showcasing more about Apple's Internal Settings for your Mac

> You can `copy` and `paste` (copy-pasta) the following command in OS X Terminal:
### EXAMPLE:
![image](https://github.com/JayRizzo/MacDefaults/assets/22861678/873b5e1c-79ed-4f72-ba45-6e949e9a5a14)

-----------------------
-----------------------
-----------------------

# Update Mac Settings

## Set Screenshot Capture Behaviour.
> When pressing the commands for a screen shot:

> <kbd>COMMAND</kbd><kbd>SHIFT</kbd><kbd>3</kbd>: for a full screenshot

> <kbd>COMMAND</kbd><kbd>SHIFT</kbd><kbd>4</kbd>: for a custom screenshot click and drag.

> <kbd>COMMAND</kbd><kbd>SHIFT</kbd><kbd>4</kbd> then press the <kbd>SPACE BAR</kbd> then hover over a Window or open program to auto resize the screenshot image.

```bash
defaults write com.apple.screencapture name ""                           # remove the word screenshot from the images.
defaults write com.apple.screencapture type png                          # sets the image file extension to PNG format.
defaults write com.apple.screencapture include-date -bool true           # Include the date in your screenshot name
defaults write com.apple.screencapture disable-shadow -bool true         # Disable the default image shadow around your screenshots
mkdir ~/Pictures/Screenshots                                             # ignore error if already exists.
defaults write com.apple.screencapture location ~/Pictures/Screenshots   # Set the default location to the folder listed above.
killall SystemUIServer                                                   # You must Kill the SystemUI to ensure your changes are reflected. (this does not harm your computer, it auto relaunch.)
```
### EXAMPLE:
![image](https://github.com/JayRizzo/MacDefaults/assets/22861678/34feb5f3-9955-495b-8a11-fb197c7226c4)

-----------------------
-----------------------
-----------------------

# ENABLE The Expand Save Panel By Default
```bash
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool true
killall SystemUIServer
```

### EXAMPLE:
![image](https://github.com/JayRizzo/MacDefaults/assets/22861678/ea1f399d-5632-4c62-8645-eef2496136e9)


# DISABLE The Expand Save Panel By Default
```bash
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool false
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool false
killall SystemUIServer
```
### EXAMPLE: 
![image](https://github.com/JayRizzo/MacDefaults/assets/22861678/54fd67ea-0a60-4f53-b1d6-7092f1639e72)


-----------------------
-----------------------
-----------------------
# Show Full Name at Login.

```bash
defaults write com.apple.loginwindow SHOWFULLNAME -bool true

# Set Hint to come up after 10 tries, instead of default of 3.
sudo defaults write /Library/Preferences/com.apple.loginwindow RetriesUntilHint 10

# Do not auto seek bluetooth.
sudo defaults write /Library/Preferences/com.apple.Bluetooth BluetoothAutoSeekKeyboard -bool false
sudo defaults write /Library/Preferences/com.apple.Bluetooth BluetoothAutoSeekPointingDevice -bool false

# =============================================================================

```
