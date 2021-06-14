# CLI Tools

Add command description via `tldr`, then strip ansi with https://maxschmitt.me/ansistrip/ rather than install some weird tool or use regex magic.

```
$ tldr <command> >> README.md
```

- [CLI Tools](#cli-tools)
  - [Resources](#resources)
    - [Tools](#tools)
    - [Explain Shit](#explain-shit)
  - [`fzf`](#fzf)
  - [`fd`](#fd)
  - [`rg`](#rg)
  - [`jl`](#jl)
  - [`bat`](#bat)
  - [`exa`](#exa)
  - [`http`](#http)
  - [`tree`](#tree)
  - [`tldr`](#tldr)
  - [`vd` (visidata)](#vd-visidata)
  - [`gron`](#gron)
  - [`btm`](#btm)
  - [`hexyl`](#hexyl)
  - [`procs`](#procs)

## Resources

### Tools
https://github.com/ibraheemdev/modern-unix
https://darrenburns.net/posts/tools/
https://darrenburns.net/posts/more-tools
https://darrenburns.net/posts/even-more-tools

### Explain Shit

https://explainshell.com/
https://regexr.com/
https://crontab.guru/

## `fzf`

Command-line fuzzy finder.
Similar to `sk`.
More information: <https://github.com/junegunn/fzf>.

- Start fzf on all files in the specified directory:
    `find path/to/directory -type f | fzf`

- Start fzf for running processes:
    `ps aux | fzf`

- Select multiple files with `Shift + Tab` and write to a file:
    `find path/to/directory -type f | fzf --multi > filename`

- Start fzf with a specified query:
    `fzf --query "query"`

- Start fzf on entries that start with core and end with either go, rb, or py:
    `fzf --query "^core go$ | rb$ | py$"`

- Start fzf on entries that not match pyc and match exactly travis:
    `fzf --query "!pyc 'travis"`

## `fd`

An alternative to `find`.
Aims to be faster and easier to use than `find`.
More information: <https://github.com/sharkdp/fd>.

- Recursively find files matching the given pattern in the current directory:
    `fd pattern`

- Find files that begin with "foo":
    `fd '^foo'`

- Find files with a specific extension:
    `fd --extension txt`

- Find files in a specific directory:
    `fd pattern path/to/directory`

- Include ignored and hidden files in the search:
    `fd --hidden --no-ignore pattern`

- Execute a command on each search result returned:
    `fd pattern --exec command`
This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

## `rg`

Ripgrep is a recursive line-oriented CLI search tool.
Aims to be a faster alternative to `grep`.
More information: <https://github.com/BurntSushi/ripgrep>.

- Recursively search the current directory for a regular expression:
    `rg regular_expression`

- Search for regular expressions recursively in the current directory, including hidden files and files listed in `.gitignore`:
    `rg --no-ignore --hidden regular_expression`

- Search for a regular expression only in a certain filetype (e.g., html, css, etc.):
    `rg --type filetype regular_expression`

- Search for a regular expression only in a subset of directories:
    `rg regular_expression set_of_subdirs`

- Search for a regular expression in files matching a glob (e.g., `README.*`):
    `rg regular_expression --glob glob`

- Only list matched files (useful when piping to other commands):
    `rg --files-with-matches regular_expression`

- Show lines that do not match the given regular expression:
    `rg --invert-match regular_expression`

- Search a literal string pattern:
    `rg --fixed-strings -- string`

## `jl`

This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

## `bat`

Print and concatenate files.
A `cat` clone with syntax highlighting and Git integration.
More information: <https://github.com/sharkdp/bat>.

- Print the contents of a file to the standard output:
    `bat file`

- Concatenate several files into the target file:
    `bat file1 file2 > target_file`

- Append several files into the target file:
    `bat file1 file2 >> target_file`

- Number all output lines:
    `bat -n file`

- Syntax highlight a json file:
    `bat --language json file.json`

- Display all supported languages:
    `bat --list-languages`

## `exa`

A modern replacement for `ls` (List directory contents).
More information: <https://the.exa.website>.

- List files one per line:
    `exa --oneline`

- List all files, including hidden files:
    `exa --all`

- Long format list (permissions, ownership, size and modification date) of all files:
    `exa --long --all`

- List files with the largest at the top:
    `exa --reverse --sort=size`

- Display a tree of files, three levels deep:
    `exa --long --tree --level=3`

- List files sorted by modification date (oldest first):
    `exa --long --sort=modified`

- List files with their headers, icons, and Git statuses:
    `exa --long --header --icons --git`

- Don't list files mentioned in `.gitignore`:
    `exa --git-ignore`

## `http`

HTTPie: HTTP client, aims to be easier to use than cURL.
More information: <https://httpie.org>.

- Download a URL to a file:
    `http --download example.org`

- Send form-encoded data:
    `http --form example.org name='bob' profile_picture@'bob.png'`

- Send JSON object:
    `http example.org name='bob'`

- Specify an HTTP method:
    `http HEAD example.org`

- Include an extra header:
    `http example.org X-MyHeader:123`

- Pass a user name and password for server authentication:
    `http --auth username:password example.org`

- Specify raw request body via stdin:
    `cat data.txt | http PUT example.org`

## `tree`

Show the contents of the current directory as a tree.
More information: <http://mama.indstate.edu/users/ice/tree/>.

- Print files and directories up to 'num' levels of depth (where 1 means the current directory):
    `tree -L num`

- Print directories only:
    `tree -d`

- Print hidden files too with colorization on:
    `tree -a -C`

- Print the tree without indentation lines, showing the full path instead (use `-N` to not escape whitespace and special characters):
    `tree -i -f`

- Print the size of each node next to it, in human-readable format, with directories displaying their cumulative size (as in the `du` command):
    `tree -s -h --du`

- Print files within the tree hierarchy, using a wildcard (glob) pattern, and pruning out directories that don't contain matching files:
    `tree -P '*.txt' --prune`

- Print directories within the tree hierarchy, using the wildcard (glob) pattern, and pruning out directories that aren't ancestors of the wanted one:
    `tree -P directory_name --matchdirs --prune`

- Print the tree ignoring the given directories:
    `tree -I 'directory_name1|directory_name2'`

## `tldr`

Displays simple help pages for command-line tools, from the tldr-pages project.
More information: <https://tldr.sh>.

- Show the tldr page for a command (hint: this is how you got here!):
    `tldr command`

- Show the tldr page for `cd`, overriding the default platform:
    `tldr -p android|linux|osx|sunos|windows cd`

- Show the tldr page for a subcommand:
    `tldr git-checkout`

- Update local pages (if the client supports caching):
    `tldr -u`

## `vd` (visidata)

This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

## `gron`

This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

## `btm`

An alternative to `top`.
Aims to be lightweight, cross-platform and more graphical than `top`.
More information: <https://github.com/ClementTsang/bottom>.

- Show the default layout (cpu, memory, temperatures, disk, network, and processes):
    `btm`

- Enable basic mode, removing charts and condensing data (similar to `top`):
    `btm --basic`

- Use big dots instead of small ones in charts:
    `btm --dot_marker`

- Show also battery charge and health status:
    `btm --battery`

- Refresh every 250 milliseconds and show the last 30 seconds in the charts:
    `btm --rate 250 --default_time_value 30000`

## `hexyl`

A simple hex viewer for the terminal. Uses colored output to distinguish different categories of bytes.
More information: <https://github.com/sharkdp/hexyl>.

- Print the hexadecimal representation of a file:
    `hexyl path/to/file`

- Print the hexadecimal representation of the first n bytes of a file:
    `hexyl -n n path/to/file`

- Print bytes 512 through 1024 of a file:
    `hexyl -r 512:1024 path/to/file`

- Print 512 bytes starting at the 1024th byte:
    `hexyl -r 1024:+512 path/to/file`

## `procs`

This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr
