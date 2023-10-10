# tmux
![tmux](./images/tmux_logo.png)
### Introduction

> `tmux` is a terminal multiplexer that allows you to manage multiple terminal sessions within a single window.
It's very useful for remote work, long-running tasks, and terminal-based multitasking. 
Here's a basic guide on how to use `tmux`:

### Installation:
Install `tmux` on your system using the package manager.
```bash
# On Ubuntu/Debian:
sudo apt-get install tmux

# On CentOS/RHEL:
sudo yum install tmux

# On Fedora:
sudo dnf install tmux

# On macOS (using Homebrew):
brew install tmux
```

### Basic Usage:

1. **Starting a new tmux session:**
   ```bash
   tmux
   ```
   or start a new named session:
   ```bash
   tmux new -s session_name
   ```

2. **Detaching from a tmux session:**
   Press `Ctrl + b` followed by `d`.

3. **Re-attaching to an existing tmux session:**
   ```bash
   tmux attach -t session_name
   ```

4. **Listing all tmux sessions:**
   ```bash
   tmux ls
   ```

5. **Killing a tmux session:**
   ```bash
   tmux kill-session -t session_name
   ```

6. **list all key bindings:**(very useful)
   ```bash
    prefix + ?

   ```
    

### Window Management:

1. **Creating a new window:**
   Press `Ctrl + b` followed by `c`.

2. **Switching between windows:**
   Press `Ctrl + b` followed by window number (e.g., `0` for the first window).

3. **Renaming a window:**
   Press `Ctrl + b` followed by `,`.

4. **Closing a window:**
   Exit all the shells in the window.

### Pane Management:

1. **Splitting panes:**
   - Horizontal Split: `Ctrl + b` followed by `%`.
   - Vertical Split: `Ctrl + b` followed by `"`.

2. **Switching between panes:**
   Press `Ctrl + b` followed by arrow keys.

3. **Resizing panes:**
   Press `Ctrl + b` followed by `Ctrl` + arrow keys.

4. **Closing a pane:**
   Exit the shell in the pane.

### Customization and Configuration:
`tmux` is highly configurable through a file named `.tmux.conf` located in your home directory. You can change key bindings, colors, and other settings
by defining them in this file.

`tmux` uses a series of commands and options to customize its behavior. Among them,`set-option` and `bind-key` are two commonly used commands.

+ **set-option**(its abbreviation **set**)
    > set-option allows you to modify various configuration options of tmux. These options control many aspects of tmux, from its appearance to its specific behaviors.
    > The -g flag means the setting is global. Without this flag, settings typically only affect the current window or pane.
    > + Examples:<br>
    > `set -g status-bg blue`: Sets the background color of the status bar to blue.<br>
    > `set -g mouse on`: Enables mouse support.
+ **bind-key**(its abbreviation **bind**)
    > The bind command is used to bind specific keys or key combinations to `tmux` commands. This allows you to create or modify shortcuts, making the operation of `tmux` more seamless.
    > + Examples:<br>
    > `bind C-a send-prefix`: Sends the prefix command when Ctrl+a is pressed (useful when changing the default prefix). <br>
    > `bind r source-file ~/.tmux.conf`: Binds the r key to the command that reloads the tmux configuration file. <br>

Tmux plugins can be easily managed and installed using `tpm`(tmux Plugin Manager).Here are some steps how to set up and use tmp:
1. Install tpm
> Run the following command in your terminal to clone tpm to the default plugins path:
```bash
    git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```
2. Initialize tpm in ~/.tmux.conf:
> Add the following lines to the bottom of your tmux configuration file ~/.tmux.conf to initialize tpm:
```bash
    # list of plugins
    set -g @plugin 'tmux-plugins/tpm'
    set -g @plugin 'erikw/tmux-powerline'

    # other examples:
    # set -g @plugin 'github_username/plugin_name'
    # set -g @plugin 'github_username/plugin_name#branch'
    # set -g @plugin 'git@github.com:user/plugin'
    # set -g @plugin 'git@bitbucket.com:user/plugin'
    
    # initialize tmux plugin manager (keep this line at the very bottom of tmux.conf)
    run '~/.tmux/plugins/tpm/tpm'

```
3. Reload TMUX environment so TPM is sourced:
```bash
    # type this in terminal if tmux is already running
    tmux source ~/.tmux.conf
```

4. Installing plugins
    1. Add new plugin to ~/.tmux.conf with set -g @plugin '...'
    2. Press prefix + I (capital i, as in Install) to fetch the plugin.
The plugin was cloned to ~/.tmux/plugins/ dir and sourced.

5. Uninstalling plugins
    1. Remove (or comment out) plugin from the list.
    2. Press prefix + alt + u (lowercase u as in uninstall) to remove the plugin.

6. Key bindings

    `prefix` + `I`: 
    + Installs new plugins from GitHub or any other git repository
    + Refreshes TMUX environment

    `prefix` + `U`:
    + updates plugin(s)

    `prefix` + `alt` + `u`:
    + remove/uninstall plugins not on the plugin list


### Advanced Usage:
`tmux` also supports scripting, session sharing, and many other advanced features. As you get more comfortable with `tmux`, you can explore these features to improve 
your workflow.

This guide covers the basics, but `tmux` is a powerful tool with a lot more to offer as you become more familiar with it.







