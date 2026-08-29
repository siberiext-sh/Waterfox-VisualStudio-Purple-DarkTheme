# How to Add a Custom `userChrome.css` Theme to Waterfox

This guide explains how to install a custom `userChrome.css` file in Waterfox so you can customize the browser UI.

## 1. Enable custom CSS

Open Waterfox and type this into the address bar:

```text
about:config
```

Search for:

```text
toolkit.legacyUserProfileCustomizations.stylesheets
```

Set it to (happens to be true on default):

```text
true
```

## 2. Open your Waterfox profile folder

Open:

```text
about:support
```

Find:

```text
Profile Folder
```

Then click:

```text
Open Folder
```

This opens the active Waterfox profile directory.

## 3. Create the `chrome` folder

Inside your profile folder, create a new folder named:

```text
chrome
```

The structure should look like this:

```text
Your Waterfox Profile
├── prefs.js
├── places.sqlite
├── ...
└── chrome
```

## 4. Create `userChrome.css`

Inside the `chrome` folder, create a file named:

```text
userChrome.css
```

Make sure Windows did not save it as:

```text
userChrome.css.txt
```

To verify this in Windows Explorer, enable:

```text
View → Show → File name extensions
```

Your final structure should be:

```text
Your Waterfox Profile
└── chrome
    └── userChrome.css
```

## 5. Paste your custom CSS

Open `userChrome.css` in a text editor such as VS Code or Notepad.

Paste your Waterfox UI CSS into the file and save it.

Example:

```css
:root {
    --bg-root: #050507;
    --bg-toolbar: #09090d;
    --purple-main: #8653e6;
    --purple-bright: #9b6cff;
}

#main-window {
    background: var(--bg-root) !important;
}

#nav-bar {
    background: var(--bg-toolbar) !important;
}

#urlbar[focused] #urlbar-background {
    border-color: var(--purple-main) !important;
}
```

## 6. Restart Waterfox

Fully close Waterfox and start it again.

The custom `userChrome.css` should now be applied.

If you change the CSS later, save the file and restart Waterfox again to see the changes.

## Optional: Customize web pages too

`userChrome.css` changes the Waterfox browser interface itself.

If you also want to customize internal pages such as the Waterfox New Tab page, create another file in the same `chrome` folder:

```text
userContent.css
```

Your folder can then look like this:

```text
Your Waterfox Profile
└── chrome
    ├── userChrome.css
    └── userContent.css
```

## Troubleshooting

If the theme does not load:

- Check that `toolkit.legacyUserProfileCustomizations.stylesheets` is set to `true`.
- Check that the folder is named exactly `chrome`.
- Check that the file is named exactly `userChrome.css`.
- Make sure the file is not actually `userChrome.css.txt`.
- Confirm you edited the profile shown in `about:support`.
- Fully restart Waterfox after each change.
