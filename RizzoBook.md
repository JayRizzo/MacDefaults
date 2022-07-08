# My Settings

```bash

# =============================================================================
# Update Mac Settings
# =============================================================================
# Set Screenshot Capture Behaviour.
defaults write com.apple.screencapture type png
defaults write com.apple.screencapture include-date -bool true
defaults write com.apple.screencapture disable-shadow -bool true
mkdir ~/Pictures/Screenshots # ignore error if already exists.
defaults write com.apple.screencapture location ~/Pictures/Screenshots
killall SystemUIServer

# Enable the expand save panel by default
# Copy and paste the following command in OS X Terminal:
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode2 -bool true
killall SystemUIServer

# Show Full Name at Login.
defaults write com.apple.loginwindow SHOWFULLNAME -bool true
# Set Hint to come up after 10 tries, instead of default of 3.
sudo defaults write /Library/Preferences/com.apple.loginwindow RetriesUntilHint 10

# Do not auto seek bluetooth.
sudo defaults write /Library/Preferences/com.apple.Bluetooth BluetoothAutoSeekKeyboard -bool false
sudo defaults write /Library/Preferences/com.apple.Bluetooth BluetoothAutoSeekPointingDevice -bool false

# =============================================================================

```
