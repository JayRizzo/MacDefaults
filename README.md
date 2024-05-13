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
![image](https://github.com/JayRizzo/MacDefaults/assets/22861678/004fe18b-de9f-4559-88ac-a7517d20084a)
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

-----------------------
###### WIP
-----------------------

```bash
# SOURCE: https://macos.gadgethacks.com/how-to/6-tweaks-you-should-be-using-your-mac-right-now-0161605/
sudo nvram SystemAudioVolume="%00"      # Disable the Boot Up Sound

defaults write com.apple.Dock autohide-delay -float 0                               # Make Your Dock Appear Faster
defaults write com.apple.dock autohide-time-modifier -float 0.5                     # Make Your Dock Appear Faster
killall Dock                                                                        # Make Your Dock Appear Faster
defaults write com.apple.finder QLEnableTextSelection -bool TRUE                    # Select Text While in Quick Look
killall Finder                                                                      # Select Text While in Quick Look
find TargetDirectory/ -mindepth 2 -type f -exec mv -i '{}' TargetDirectory/ ';'     # Flatten Any Directory Down to One Folder


# SHOW SAVE AS "EXPANDED" "SAVE AS WINDOW"
    defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true && \
    defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool true && \
    defaults write NSGlobalDomain PMPrintingExpandedStateForPrint -bool true && \
    defaults write NSGlobalDomain PMPrintingExpandedStateForPrint2 -bool true

# SHOW SAVE AS "SHORTENED" "SAVE AS WINDOW"
    defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool false && \
    defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool false && \
    defaults write NSGlobalDomain PMPrintingExpandedStateForPrint -bool false && \
    defaults write NSGlobalDomain PMPrintingExpandedStateForPrint2 -bool false

# SOURCE: https://onethingwell.org/post/28343756945/dot-osx
    defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true     # EXPAND SAVE PANEL BY DEFAULT
    defaults write NSGlobalDomain AppleKeyboardUIMode -int 3                        # ENABLE FULL KEYBOARD ACCESS FOR ALL CONTROLS AKA. ENABLE TAB IN MODAL DIALOGS
    defaults write NSGlobalDomain NSAutomaticSpellingCorrectionEnabled -bool false  # DISABLE AUTO-CORRECT
    defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false      # Disable the warning when changing a file extension
    chflags nohidden ~/Library                                                      # Show the ~/Library folder
    defaults write com.apple.dock "dashboard-in-overlay" -bool true                 # Don’t show Dashboard as a Space
    defaults write com.apple.finder QLEnableTextSelection -bool true                # Finder: allow text selection in Quick Look

# SOURCE: https://medium.com/swlh/top-mac-os-default-behaviors-you-should-consider-changing-419b679fe290
    defaults write -g AppleShowAllExtensions -bool true                             # Show File Extensions
    defaults write com.apple.finder AppleShowAllFiles true                          # Show Hidden Files
    defaults write com.apple.finder ShowPathbar -bool true                          # Advanced Option: Show Path Bar
    defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"             # Always Search Within Folder
    defaults write com.apple.dock expose-animation-duration -float 0.05             # Speed up Animations for App Expose
    defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true    # Disable .DS_Store File Creation
    defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true        # Disable .DS_Store Creation on all External Media
    defaults write -g NSAutomaticSpellingCorrectionEnabled -bool false              # Disable AutoCorrect
    defaults write -g KeyRepeat -int 0.5                                            # Key Repeat Frequency (default is 2)
    defaults write -g InitialKeyRepeat -int 10                                      #  When the Key repeat starts(default is 15 or 225ms)
    defaults write NSGlobalDomain NSAutomaticCapitalizationEnabled -bool false      # Disables auto capitalization
    defaults write NSGlobalDomain NSAutomaticDashSubstitutionEnabled -bool false    # Disables "smart" dashes
    defaults write NSGlobalDomain NSAutomaticPeriodSubstitutionEnabled -bool false  # Disables automatic period substitutions
    defaults write NSGlobalDomain NSAutomaticQuoteSubstitutionEnabled -bool false   # Disables smart quotes 
    defaults write -g AppleShowScrollBars -string "Always"                          # Always Show Scrollbars
    defaults write com.apple.Safari HomePage -string "about:blank"                  # Safari Default Web Page to a blank page


# SOURCE: https://macos.gadgethacks.com/how-to/change-os-x-s-annoying-default-settings-using-terminal-0162471/
    defaults write NSGlobalDomain com.apple.swipescrolldirection -bool false        # Disable Natural Scrolling
    defaults write com.apple.Safari AutoOpenSafeDownloads -bool false               # Prevent Safari from Opening Safe Files Automatically

# https://macos.gadgethacks.com/how-to/13-terminal-commands-every-mac-user-should-know-0162453/
    sudo systemsetup -setrestartfreeze on                                           # Restart Your Mac Automatically After It Freezes
    defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 1                # Check for Software Updates Daily
    defaults write com.apple.finder AppleShowAllFiles -bool true                    # SHOW ALL HIDDEND FILES AND FOLDERS
    chflags nohidden ~/Library/                                                     # Unhide Files & Folders Individually
    chflags hidden ~/Documents/Secrets                                              #   Hide Files & Folders Individually


# Automatically Open a Finder Window When a Drive Is Mounted
    defaults write com.apple.frameworks.diskimages auto-open-ro-root -bool true
    defaults write com.apple.frameworks.diskimages auto-open-rw-root -bool true
    defaults write com.apple.finder OpenWindowForNewRemovableDisk -bool true

# Securely Delete Files Individually
    srm -s /draggedfile # command uses one-pass overwriting before trashing
    srm -m /draggedfile # command uses SEVEN-pass overwriting before trashing
    srm -rf /draggedfolder # REMOVES FOLDER

    defaults write com.apple.mail NSUserKeyEquivalents -dict-add "Send" -string "@\\U21a9?"  # Add Send Shortcut to the OS X Mail App
    defaults write com.apple.messageshelper.MessageController SOInputLineSettings -dict-add "automaticEmojiSubstitutionEnablediMessage" -bool false  # Disable Automatic Emoji Substitution




```




