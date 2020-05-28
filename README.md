# NeomuttFilePicker
Attach files in (neo)mutt using [Ranger](https://github.com/ranger/ranger) or [Vifm](https://github.com/vifm) as your file menager.

This scrip is based on the [this topic](https://www.reddit.com/r/commandline/comments/cbxvdf/combine_neomutt_with_ranger/) and improved to allow attaching mulptiple files with spaces in the name and path.

## Instalation
1) Copy the "filepicker" file to your .config/mutt or wherewher is your config directory.
2) Add the following line to your .muttrc so that you can attach files with `A`

```
macro compose A "<shell-escape>bash $HOME/.config/mutt/filepick<enter><enter-command>source $HOME/.config/mutt/tmpfile<enter><shell-escape>bash $HOME/.config/mutt/filepick clean<enter>" "Attach with your file menager"
```

## Settings
In the "filepicker" file you can choose which file manager to use. Vifm by default, but you can uncomment Ranger and comment Vifm if you like.
