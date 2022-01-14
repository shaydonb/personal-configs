# Keyboard Shortcuts
This document will be a quick reference for useful keyboard shortcuts, that while cannot be used everywhere, can me used in most shells and allows for a better chance for one who knows them to be a true keyboard wizard who can navigate code and a command line interface better than Ferdinand Magellan could the 7 seas.

## General
### `Ctrl + a`: Beginning of Line
This shortcut brings you to the beginning of the current line of text being edited.

### `Ctrl + e`: End of Line
This shortcut brings you to the end of the current line of text being edited.

### `Ctrl + k`: Delete After Cursor
This shortcut deletes everything to the right of the cursor on the current line of text being edited.

### `Ctrl + c`: Kill Process
This shortcut sends a SIGINT signal to the currently running process (number 9 of the signals as indexed by `top`), which serves to kill whatever the current foreground process is in the command line, if any.

### `Ctrl + z`: Pause Process
This shortcute sends a SIGTSTP signal to the currently running process (number 20 of the signals as indexed in `top`), which serves to pause execution of whatever the current foreground process is in the command line, if any. Restart the process in the foreground by running `fg` or the background by running `bg`.

