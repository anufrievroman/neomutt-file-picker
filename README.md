# NeomuttFilePicker

- Attach files to your emails in [NeoMutt](https://github.com/neomutt/) using [Ranger](https://github.com/ranger/ranger) or [Vifm](https://github.com/vifm) as your file manager.
- Choose a directory to store attachments with Ranger or Vifm

The main script is based on the [this topic](https://www.reddit.com/r/commandline/comments/cbxvdf/combine_neomutt_with_ranger/) and improved to allow attaching mulptiple files with spaces in the name and path.

## Usage of Filepicker

1. Copy the `filepicker` file to your `.config/mutt` or wherewher is your config directory.
2. Add the following line to your `.muttrc` so that you can attach files with `A`

```
macro compose A "<shell-escape>bash $HOME/.config/mutt/filepicker<enter><enter-command>source $HOME/.config/mutt/tmpfile<enter><shell-escape>bash $HOME/.config/mutt/filepicker clean<enter>" "Attach with your file manager"
```
3. Now, on the email sending screen (when you already wrote the text and saved it) type `A` instead of standard `a` to call the script. The file manager should appear. Choose files that you want to attach (tag them if multiple files) and hit Enter. Hit Enter twice more when asked. 

## Usage of Dirpicker

1. Copy the `dirpicker` file to your `.config/mutt` or wherewher is your config directory.
2. Add the following line to your `.muttrc` so that you can choose the folder
   where to store files with `S`

```
macro attach S "<shell-escape>bash $HOME/.config/mutt/dirpicker<enter><enter-command>source $HOME/.config/mutt/tmpfile<enter>o" "Choose folder with ranger"
```
3. Now, on the attachment screen (by default, reached with `v`), type `S` instead of standard `s` to call the script. The file manager should appear. Choose the folder with ranger, quit with `q`. Mutt may then ask for the filename in the folder. 

## Settings

In the `filepicker` and `dirpicker` files you can choose which file manager to use. Ranger by default, but you can uncomment Vifm and comment Ranger if you like.

## Issues
- You should start NeoMutt from your home directory, otherwise you won't be able to attach files.
- You might need to make the script executable if you have error about permissions.

## TODO 

- The dirpicker should be adapted to handle several attachments at once (perhaps with ripmime or munpack?)
