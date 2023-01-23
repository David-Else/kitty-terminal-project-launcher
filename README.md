## kitty-terminal-project-launcher

Easily open and manage your local coding projects with
[kitty terminal](https://github.com/kovidgoyal/kitty).

### Features:

- Fuzzy search for all or just recent projects using
  [fzf](https://github.com/junegunn/fzf).
- Open projects with your default terminal editor.
- Open preconfigured sets of named windows for different project types.
- Automatic closing of windows when exiting your editor.
- Implimented in only 47 lines of shell script.

### Configuration

1. Edit:

```sh
a) items=$(find ~/Documents/business ~/Documents/personal ~/Documents/apps-sites -maxdepth 2 -mindepth 1 -type d) ;;
```

To use the folders that contain your projects, and alter `maxdepth 2` if
required.

2. Decide on which windows to open based on which files or directories are in
   the project root, for example, to open an additional terminal window for Rust
   and TypeScript projects the included default is:

```sh
    if [ -f "Cargo.toml" ] || [ -f "package.json" ]; then
        kitty @ launch --title "Terminal:$project_name" --keep-focus --cwd="$selected_dir"
    fi
```

### Usage:

1. Copy the `ep` script into your `$PATH`.
2. Run the command `ep` in your terminal.
3. Follow the prompts to search and open your desired project.
4. Start coding in your preconfigured and organized workspace.

Requirements:

- [kitty terminal](https://github.com/kovidgoyal/kitty).
- [fzf](https://github.com/junegunn/fzf).
