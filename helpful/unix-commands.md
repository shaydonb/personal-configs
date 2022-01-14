# Unix Commands
Useful for MacOS, Linux, Unix itself, and generally any Unix-derived operating system, these commands and combinations of commands can be incredibly helpful for doing common tasks on the command line interface.

These items will be separated out by category as best as possible, but it may not always be perfect as some things will overlap and be useful in other areas as well. That said, it should be fairly straightforward, and should be alphabetized by both category and individual command. As this document grows, navigation of it may very well become more difficult, but alternatives are just constantly looking stuff up anyways, so this document is to serve as a quick reference in part, but also as a place to just collect thoughts on certain Unix commands and workflows that have come in handy or would be worth using as "power user" status increases. The collection of these thoughts would hopefully also lend naturally to the eventual learning and memorization of these commands anyways.

## Directory Navigation
### `pushd``and `popd`
These commands are features of the Bash shell, and can aid greatly in the rapid navigation between directory paths in any larger number than 2. This is because it creates a stack data structure of the directories you have navigated to, in the order you navigated to them. Every time `pushd` is used, it adds both the current working directory, and the directory the user moved to onto the stack of paths. For example:
```
$ pwd
one
$ pushd two/three
~/one/two/three ~/one
$ pwd
three
$ pushd four
~/one/two/three/four ~/one/two/three ~/one
$ pushd five
~/one/two/three/four/five ~/one/two/three/four ~/one/two/three ~/one
```
Notice how with each new switch, chain gets longer, or really the stack gets taller. This stack can then be navigated, via indexes in the stack or via `popd`, which can either remove items by index with or without actually navigating to them, or can even navigate to and remove the top of the stack implicitly with a single, simple `popd` call.

The stack can be rotated by certain amounts using indexes relative to either the top (left) or bottom (right) end of the stack. To go to the first (top/leftmost) item in the stack, use `pushd +0`, and to go to the last (which rotates the bottom/rightmost/last stack directory to the top), use `pushd -0`.

In order to remove items from the stack by index, `popd -<index>` in order to index relative to the bottom/rightmost/last item on the stack, and use `popd +<index>` to index the directory removal from the item at the top/leftmost/front of the stack.

In order to see a full list of directories and their indices (relative to the top of the stack), use `dirs -v`.

The directory stack will stick around indefinitely so long as you remain within the same terminal session.

For more information on the use of these
