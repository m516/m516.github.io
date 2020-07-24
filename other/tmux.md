# Using Tmux on Linux

I was running some processes on a headless Pi 0W that take a long time. This was frusturating
because I used SSH to establish a connection to the terminal on the Pi. Fortunately, I found 
that Tmux is a terminal emulator that can easily attach and detach to processes, and I can run
any number of projects without holding an SSH connection.

## Installation on the Pi/Nvidia Jetson
Tmux is an `apt` package, so it can be installed with the following command: `sudo apt-get install tmux`

## Interesting commands
### In/Out of Tmux
* `tmux new-session -s session-name` creates a new session called *session-name*
* `tmux ls` lists all open sessions
* `tmux attach-session [-t session-name]` attaches to a session with the name *session-name* if 
`-t session-name` is given. Otherwise it binds to the most recently used session.
* `tmux kill-session [-t session-name]` works like *attach-session*, but kills sessions instead

### In Tmux
* `Ctrl+b s` shows an interactive list of sessions. Pressing <enter> enters into the selected session.
This interactive list has its own subcommands, **each beginning with `:**
  * `attach-session` attaches to the selected session
  * `kills-session` kills the selected session
* `Ctrl+B d` detaches from the current session
* Panes
  * `Ctrl+B "` splits the current pane horizontally into to vertically arranged panes
  * `Ctrl+B %` splits the current pane vertically into to horizontally arranged panes
  * `Ctrl+B <arrow key>` navigates through the panes
  * `Ctrl+B Q` briefly shows pane numbers
  * `Ctrl+B O` moves through panes in order of their number.
  * `Ctrl+B X` kills and removes the pane
## Sources
https://unix.stackexchange.com/questions/174440/exit-tmux-window-without-quitting-the-terminal-program

https://github.com/tldr-pages/tldr/blob/master/pages/common/tmux.md

https://www.howtogeek.com/662422/how-to-use-linuxs-screen-command/

experience
