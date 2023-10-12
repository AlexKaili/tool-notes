### Using Ranger: A Guide

**Ranger** is a powerful and efficient file manager that works in the terminal and uses Vim keybindings. It allows you to navigate your file system and perform common file management tasks without leaving the terminal.

### Installation

Ranger is available in most Linux distribution repositories and can be installed using the package manager:

- **Ubuntu/Debian**: 
  ```bash
  sudo apt-get install ranger
  ```
- **Fedora**:
  ```bash
  sudo dnf install ranger
  ```
- **Arch Linux**:
  ```bash
  sudo pacman -S ranger
  ```
- **MacOS**:
    ```bash
    brew install ranger
    ```
### Basic Navigation

- **Navigate through directories**: 
  - `j`: Move down.
  - `k`: Move up.
  - `h`: Go to the parent directory.
  - `l` or `Enter`: Go to the selected directory.

- **File Operations**: 
  - `yy`: Yank (copy) a file or directory.
  - `dd`: Delete the selected file or directory.
  - `pp`: Paste yanked/copied files or directories.
  
- **Opening Files**:
  - `Enter`: Opens the selected file with the default application.
  
- **Tabs**:
  - `gn`: Create a new tab.
  - `gt`: Go to the next tab.
  - `gT`: Go to the previous tab.

### File Preview and Manipulation

- **Previewing Files**: 
  - `v`: Visual mode for selecting multiple files.
  - `space`: Select the highlighted file/directory while in visual mode.
  
- **Creating Files/Directories**:
  - `:touch <filename>`: Create a new file.
  - `:mkdir <directory_name>`: Create a new directory.

### Searching and Sorting

- **Searching**:
  - `/`: Begin a filename search.
  - `n`: Find the next match.
  - `N`: Find the previous match.
  
- **Sorting**:
  - `o`: Cycle through sorting options (name, size, type, etc.)
  - `O`: Reverse the sort order.
  
### Configuration

Ranger can be customized and configured by editing its configuration files, which can be generated using the following command:
```bash
ranger --copy-config=all
```
This will copy the configuration files to `~/.config/ranger/`. You can edit `rc.conf` for keybindings and `rifle.conf` for determining which programs to open files with.

### Extend Functionality with Plugins

Ranger supports plugins and has several developed by its community. To use a plugin, you typically clone the plugin's repository into `~/.config/ranger/plugins/` and the plugin will be available next time you run ranger.

### Conclusion

This guide provides a basic overview of using Ranger, and there's more functionality to explore via its man page (`man ranger`) or by pressing `?` within Ranger for context-sensitive help. Navigate, explore, and get familiar with its capabilities to efficiently manage files in the terminal!


