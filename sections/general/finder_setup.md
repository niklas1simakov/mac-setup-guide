[README](../../README.md) > [General](general_overview.md) > [Finder Setup](finder_setup.md)

# Finder Setup

## Essentials

### Finder Settings

- [ ] Adjust Sidebar in Settings to show (Settings > Sidebar):
  - Applications
  - Downloads
  - User Home
  - Macintosh HD
  - ... whichever you prefer
- [ ] Set "New Finder windows show" to "Home" or whichever you prefer (Settings > General)
- [ ] Show folders on top (Settings > Advanced > Keep folders on top > (tick) In Windows when sorting by name)
- [ ] Set "Default search scope" to "Current folder" (Settings > Advanced > Default search scope (dropdown))
- [ ] (optional) Open new folders in tabs instead of windows (Settings > General)
- [ ] (optional) Show filename extensions (Settings > Advanced > Show all filename extensions)
- should look like this after setup:

  <img src="screenshots/finder-settings-advanced.png" alt="Finder Settings Advanced" width="300px"/>

### Finder View Options (Finder > View)

- [ ] Show Path Bar (View > Show Path Bar)
- [ ] Show Status Bar (View > Show Status Bar)
- [ ] Hide Preview (View > Hide Preview)
- [ ] Set View Options (View > Show View Options)

  - as shown on the screenshot & save as default:

    <img src="screenshots/finder-show-view-options.png" alt="View Options" width="300px"/>

### Customize Toolbar

- [ ] Remove most of the toolbar buttons (Finder > View > Customize Toolbar)
- [ ] Show icons only
- My recommended setup:

<img src="screenshots/finder-customize-toolbar.png" alt="Customize Toolbar" width="800px"/>

- [ ] (advanced & optional) [Add custom toolbar buttons](finder_add_custom_buttons.md)

### Setup some cloud storage (recommended)

- [ ] (personal preference) [Onedrive](https://www.microsoft.com/en-us/microsoft-365/onedrive/online-cloud-storage) (free)
  - I like the integration with Microsoft 365 & you get 1TB of cloud storage with a subscription
- [ ] [Google Drive](https://www.google.com/drive/download/) (free)
- [ ] iCloud (free & preinstalled)

## Advanced & Optional (for developers)

### Add custom toolbar buttons

- [ ] [Add custom toolbar buttons](finder_add_custom_buttons.md)

### Finder Quick Look Extensions

Quick Look is the preview you get when you press spacebar on a file.

- [ ] PreviewText (free) [Download](https://smittytone.net/previewtext/)
  - Generate previews of textual files & files with no extensions
- [ ] (optional) PreviewCode (1$) [Download](https://smittytone.net/previewcode/)
  - Generate previews of with code highlighting supporting a buch of different languages. Natively macOS doesn't highlight code, but it does show the source code for some formats.
- [ ] (optional) PreviewMarkdown (1$) [Download](https://smittytone.net/previewmarkdown/)
  - A tool to generate previews of markdown files. Natively macOS doesn't render markdown files, but only shows the source code.
- [ ] (optional) PreviewJSON (1$) [Download](https://smittytone.net/previewjson/)
  - A tool to generate previews of highlighted JSON files. Natively macOS doesn't highlight JSON files, but shows the source code.

### Make Finder quitable

- To make Finder quitable, you can run the following command in the terminal. Please consider that when you quit Finder your Desktop icons will also disappear until you restart Finder. Additionally, Finder will take slightly longer to start and you will have to double click to open a finder window.
  ```sh
  osascript -e 'tell application "System Preferences" to quit'  # quit System Preferences
  defaults write com.apple.finder QuitMenuItem -bool true  # make Finder quitable
  killall Finder  # restart Finder
  ```
- to restore Finder to its default behavior, run:
  ```sh
  osascript -e 'tell application "System Preferences" to quit'  # quit System Preferences
  defaults write com.apple.finder QuitMenuItem -bool false  # restore Finder quitable
  killall Finder  # restart Finder
  ```
