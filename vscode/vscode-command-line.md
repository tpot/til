# Running Visual Studio Code Command Line on macOS

VS Code has two Command Palette commands, `Shell Command: Install 'code'
command in PATH` and `Shell Command: Uninstall 'code' command from PATH`.
Unfortunately both of these require administrator access on macOS which
isn't something available to everyone.

Here's a bash alias to run `code` without requiring the password to an
administrator account:
```
alias code="/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code"
```

Once you have this alias, you can start up a new VS Code window in the
current directory like so:
```
$ code --new-window .
```
