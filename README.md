# TF2 cfg syntax highlighting

Adds syntax highlighting support for `.cfg` files

## Features

<blockquote>
  <p><code>medic.cfg</code> adapted from b4nny's <a href="https://drive.google.com/file/d/1S9bcuSHauGUSNlrOP93zm5kOlynnWG8V/view" target="_blank">config</a>
</blockquote>
<table>
  <tr>
    <td><img src="https://i.imgur.com/SSHPKrn.png" alt="Example without syntax highlighting" /></td>
    <td><img src="https://i.imgur.com/OCPCUSP.png" alt="Example with syntax highlighting" /></td>
  </tr>
  <tr>
    <td><i>Plain Text</i></td>
    <td><i>Using the <code><b>Dark+ (default dark)</b></code> theme</i></td>
  </tr>
</table>

This is the grammar I'm tagging:

- Comment
- Command
  - Unknown (deprecated, unused, or just unknown)
  - [Buttons/Keys](https://wiki.teamfortress.com/wiki/Scripting#List_of_key_names) (`SPACE`, `MOUSE1`)
  - Actions (`+attack`, `say_team`)
  - Settings (`alias`, `bind`, `r_drawviewmodel`)
- Numeric-Literal
- Variable (custom commands)
- Macros (`"+jump; +duck; +attack;"`)
- Punctuation-Semicolon

## Install

<ol>
  <li><a href="https://code.visualstudio.com/Download">Download</a> VS Code</li>
  <li>
    <p>Install the extension</p>
    <img src="https://i.imgur.com/IeOIXzc.png" alt="Install through VS Code" height="50%" width="50%" />
  </li>
  <li>
    <p>Press reload</p>
    <img src="https://i.imgur.com/oN28TYy.png" alt="Reload VS Code" height="50%" width="50%" />
  </li>
</ol>

## Setup

<img src="https://i.imgur.com/ARqR6MK.png" height="75%" width="75%" />

1.  Open a `.cfg` file
1.  Click at the bottom right to change its "File Association" (Or press `Ctrl+K, Ctrl+M`)
1.  Select, `Configure File Association for '.cfg'...`
1.  Select `TF2 cfg` from the list

### Alternatively...

You can open your user settings (`Ctrl+,`) and add

```json
"files.associations": {
  "*.cfg": "TF2 cfg"
}
```

## Theme

Note that you can change/control the [Color Theme](https://code.visualstudio.com/docs/getstarted/themes):

<img src="https://i.imgur.com/7teYynx.png" height="75%" width="75%" />

## Known Issues

- Not [all](https://developer.valvesoftware.com/wiki/List_of_TF2_console_commands_and_variables) commands have been included yet
- Lazy regex checking, such as `r_\\w+` to mark anything that starts with `r_`, but really should only include exact commands
- My regex has not been reviewed and there's potentially a smarter way to be doing some of the things
- Ideally there'd be a custom color theme with property scope names (currently I'm using at least one `.js` name)

## Release Notes

### v0.0.7

- Renamed the settings rule to commands.
- Fixed bind and unbind key regex.
- Added regex for set* commands.
- Created a pattern for echo strings
- Fixed partial variable rule matches inside strings.
- Added several more matches for TF2, P-REC, and HLAE commands.

### v0.0.6

- Improve regex

## Unlicense

This is free is all senses of the word. [UNLICENSE](./UNLICENSE)
