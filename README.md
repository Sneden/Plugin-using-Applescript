# Plugin-using-Applescript


Created a shortcut that open all links (either hyperlinks/text links) that are copied to the clipboard to respective new tabs on the Chrome browser. 

Problem Statement :
In my task, I needed to open multiple text/ hyper links seperated by a '/n' to a new tab. The browser only offeres to open one link at a time thats selected to a new tab.

How to get it to work : 
Mapped this plugin to 'Control+T' on the keyboard through MAC settings. This was taken to the next step to save more time by mapping the 'Command+C' (to copy the links to the clipboard) and 'Control+T' (Applescript plugin) to my mouse buttons itself, this was done using USB Overdrive tool.

Perks :
Reduces time significantly by opening multiple links at a time with a click of just 2 buttons on the mouse.



Below is the script :

on run {input, parameters}
set theURLs to paragraphs of (the clipboard)
tell application "Google Chrome"
tell front window
repeat with i from 1 to the length of theURLs
set activetab to make new tab at end of tabs with properties {URL:item i of theURLs}
end repeat
end tell
end tell
end run
