# Maximize2Workspace (continued)

When I realized that the original plugin wasn't bothering to check if it was still compatible with newer versions of Gnome, I was doing that for myself and eventually figured that I should share it with the rest of the community. It looks like the plugin _may_ already be compatible with Gnome v45, but I haven't confirmed that yet. Once I have tested that out, I will push this to Gnome Extensions.

NOTE: I am testing on Debian Stable (v12/bookworm) and Testing (v13/Trixie).

## Original Plugin's Introduction

Coming from MacOS I got habituated to MacOS' style of window management when we maximize it. It allows for focussing on one thing at a time as the desktop environment gets out of your way. I wanted to use same thing in Gnome but found the suppport for it utterly lacking/non-existant. Based on attempts made by people earlier, I have tried to recreate a similar experience of maximizing minimizing full screening and closing windows as on MacOS. I would say it goes one step beyond that by remaining true to gnome's way of dealing with windows and allowing for using multi app workflows without degrading your experience. I believe this extension will work great with auto tiling enabled but I leave that to other extensions. 

This extension is limited in its scope as it does not try to change overall gnome's window management, workspace management or display management. If you want independent workspaces on your second dispaly, you will have to ask gnome for this. I have tried to keep this extension as simple as possible, code cleanup is pending, but that does not impact this extension's usability.

Check this extension out at https://extensions.gnome.org/extension/2857/maximize-to-workspace-with-history/. For best ( MacOS like ) experience set up 3/4 finger gestured to tile windows and switch workspaces.

***

Reference: 

Fork of https://github.com/rliang/gnome-shell-extension-maximize-to-workspace with added history support. Took some elements from https://github.com/satran/fullscreenworkspace-satran.in that adds some basic history tracking

***

### What does this do?
When a window is maximized this extension moves the window to the first empty workspace it can find. When it is unmaximized the window is brought back to the original workspace it was present in, if possible. Same is done when you enter full-screen or unfull-screen on you application. When you close the window you will be taken back to the workspace you opened the application in. If however you open a new app on the workspace with already maximized window and then tile the maximized window from maximized state to left or right, you won't be moved back to the original workspace, because the assumption here is that you want to work with the two applications simultaneously.

It is suggested that you use it with some sort of trackpad gesture based window tiling and navigation of workspace. I use fusuma you can use that or anything that works for you like touchegg or an extension available for gnome like https://extensions.gnome.org/extension/4245/gesture-improvements/.

To use this, I would suggest you get it from https://extensions.gnome.org/extension/2857/maximize-to-workspace-with-history/ .

***

To install run:
```
git clone https://github.com/raonetwo/MaximizeToWorkspace.git ~/.local/share/gnome-shell/extensions/maximize-to-workspace@raonetwo.github.com
gnome-extensions enable maximize-to-workspace@raonetwo.github.com
```

Then press Alt + F2 and in the dialogue box press "r" (no quotes) and enter to refresh the gnome session and verify that the extension has been enabled

***

This extension is best utilized with multi finger gestures are enabled e.g. using https://extensions.gnome.org/extension/4245/gesture-improvements/.

Or you can use keyboard shortcuts for quick navigation.

***

This has been tested on Ubuntu 19.10 on gnome version 3.34.2 and Ubuntu 20.04 on gnome 3.36, contribution are accepted for following:
1. Test it out with other gnome shell versions and update metadata.json.
2. Currently a few things are set as default like start with second workspace, no default workspace if you run out of workspaces in static workspace mode, etc. These parameters need to be exposed and set based on user preference.
3. If you find any bug in testing, want some new feature/do some basic refactoring /clean up.
