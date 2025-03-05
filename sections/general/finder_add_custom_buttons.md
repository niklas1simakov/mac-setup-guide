[README](../../README.md) > [General](general_overview.md) > [Finder Setup](finder_setup.md) > [Add Custom Buttons](finder_add_custom_buttons.md)

# Finder: Add Custom Buttons to the Toolbar

## Video Tutorial

[YouTube: Create a Mac Finder button to open project folder](https://www.youtube.com/watch?v=nQ7NErMDaKo)

## Text Tutorial (for a Mac Finder button to open project folder with Cursor)

1. Open Automator (Applications > Utilities > Automator)
2. Create a new Application
3. Add a new step: Run AppleScript
4. Add the following script:

```applescript
on run {input, parameters}
    tell application "Finder"
        set selectedItems to selection
        if (count of selectedItems) is greater than 0 then
            -- Open selected file(s) or folder(s) in Cursor.app
            set fileList to {}
            repeat with itemRef in selectedItems
                set end of fileList to POSIX path of (itemRef as alias)
            end repeat
        else
            -- Get the frontmost Finder window’s directory
            set targetFolder to target of front window as alias
            set fileList to {POSIX path of targetFolder}
        end if
    end tell

    -- Open the items in Cursor.app
    repeat with filePath in fileList
        do shell script "open -a Cursor.app " & quoted form of filePath
    end repeat
end run
```

5. Save the application as `Open in Cursor.app` (name or location is not important)
6. Go to the application in Finder (default location: Finder > Applications)
7. Hold down the `Command` key and drag the application to the Finder toolbar
8. (optional) Add a nice icon to the button
   - download an appropriate icon from the internet
   - right-click on the application and select `Get Info`
   - copy paste the icon onto the icon of the application
   - recommended: make the icon a bit smaller and add some padding as otherwise the icon will be quite big

## Some more example scripts

### Open in Terminal

Open either the selected file(s) or folder(s) or the current directory in Terminal. Always open in new tab.

```applescript
on run {input, parameters}
    tell application "Finder"
        set selectedItems to selection
        if (count of selectedItems) is greater than 0 then
            -- If a folder is selected, use its path
            set folderPath to POSIX path of (first item of selectedItems as alias)
        else
            -- If nothing is selected, use the current Finder window's path
            set folderPath to POSIX path of (target of front window as alias)
        end if
    end tell

    -- Open a new tab in Terminal
    tell application "Terminal"
        activate
        if (count of windows) is 0 then
            -- If no Terminal window is open, create a new one
            do script "cd " & quoted form of folderPath
        else
            -- If Terminal is open, create a new tab
            tell application "System Events" to tell process "Terminal"
                keystroke "t" using command down
            end tell
            -- Change to the selected folder in the new tab
            do script "cd " & quoted form of folderPath in front window
        end if
    end tell
end run
```

### Open Ghostty Terminal

Open a new tab in Ghostty Terminal.

```applescript
on run {input, parameters}
    tell application "Finder"
        set selectedItems to selection
        if (count of selectedItems) is greater than 0 then
            -- If a folder is selected, use its path
            set folderPath to POSIX path of (first item of selectedItems as alias)
        else
            -- If nothing is selected, use the current Finder window's path
            set folderPath to POSIX path of (target of front window as alias)
        end if
    end tell

    -- Open GhosttyTerminal (it supports command line parameters)
    do shell script "open -a Ghostty " & quoted form of folderPath
end run
```
