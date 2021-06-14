
[1m[39mfzf
[22m[39m
[39mCommand-line fuzzy finder.[22m[39m
[39mSimilar to `sk`.[22m[39m
[39mMore information: <https://github.com/junegunn/fzf>.[22m[39m
[32m
- Start fzf on all files in the specified directory:[22m[39m
[31m    find [22m[39m[34mpath/to/directory[39m[31m -type f | fzf[22m[39m
[32m
- Start fzf for running processes:[22m[39m
[31m    ps aux | fzf[22m[39m
[32m
- Select multiple files with `Shift + Tab` and write to a file:[22m[39m
[31m    find [22m[39m[34mpath/to/directory[39m[31m -type f | fzf --multi > [22m[39m[34mfilename[39m[31m[22m[39m
[32m
- Start fzf with a specified query:[22m[39m
[31m    fzf --query "[22m[39m[34mquery[39m[31m"[22m[39m
[32m
- Start fzf on entries that start with core and end with either go, rb, or py:[22m[39m
[31m    fzf --query "^core go$ | rb$ | py$"[22m[39m
[32m
- Start fzf on entries that not match pyc and match exactly travis:[22m[39m
[31m    fzf --query "!pyc 'travis"[22m[39m

[1m[39mfd
[22m[39m
[39mAn alternative to `find`.[22m[39m
[39mAims to be faster and easier to use than `find`.[22m[39m
[39mMore information: <https://github.com/sharkdp/fd>.[22m[39m
[32m
- Recursively find files matching the given pattern in the current directory:[22m[39m
[31m    fd [22m[39m[34mpattern[39m[31m[22m[39m
[32m
- Find files that begin with "foo":[22m[39m
[31m    fd [22m[39m[34m'^foo'[39m[31m[22m[39m
[32m
- Find files with a specific extension:[22m[39m
[31m    fd --extension [22m[39m[34mtxt[39m[31m[22m[39m
[32m
- Find files in a specific directory:[22m[39m
[31m    fd [22m[39m[34mpattern[39m[31m [22m[39m[34mpath/to/directory[39m[31m[22m[39m
[32m
- Include ignored and hidden files in the search:[22m[39m
[31m    fd --hidden --no-ignore [22m[39m[34mpattern[39m[31m[22m[39m
[32m
- Execute a command on each search result returned:[22m[39m
[31m    fd [22m[39m[34mpattern[39m[31m --exec [22m[39m[34mcommand[39m[31m[22m[39m
This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

[1m[39mrg
[22m[39m
[39mRipgrep is a recursive line-oriented CLI search tool.[22m[39m
[39mAims to be a faster alternative to `grep`.[22m[39m
[39mMore information: <https://github.com/BurntSushi/ripgrep>.[22m[39m
[32m
- Recursively search the current directory for a regular expression:[22m[39m
[31m    rg [22m[39m[34mregular_expression[39m[31m[22m[39m
[32m
- Search for regular expressions recursively in the current directory, including hidden files and files listed in `.gitignore`:[22m[39m
[31m    rg --no-ignore --hidden [22m[39m[34mregular_expression[39m[31m[22m[39m
[32m
- Search for a regular expression only in a certain filetype (e.g., html, css, etc.):[22m[39m
[31m    rg --type [22m[39m[34mfiletype[39m[31m [22m[39m[34mregular_expression[39m[31m[22m[39m
[32m
- Search for a regular expression only in a subset of directories:[22m[39m
[31m    rg [22m[39m[34mregular_expression[39m[31m [22m[39m[34mset_of_subdirs[39m[31m[22m[39m
[32m
- Search for a regular expression in files matching a glob (e.g., `README.*`):[22m[39m
[31m    rg [22m[39m[34mregular_expression[39m[31m --glob [22m[39m[34mglob[39m[31m[22m[39m
[32m
- Only list matched files (useful when piping to other commands):[22m[39m
[31m    rg --files-with-matches [22m[39m[34mregular_expression[39m[31m[22m[39m
[32m
- Show lines that do not match the given regular expression:[22m[39m
[31m    rg --invert-match [22m[39m[34mregular_expression[39m[31m[22m[39m
[32m
- Search a literal string pattern:[22m[39m
[31m    rg --fixed-strings -- [22m[39m[34mstring[39m[31m[22m[39m
This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr

[1m[39mbat
[22m[39m
[39mPrint and concatenate files.[22m[39m
[39mA `cat` clone with syntax highlighting and Git integration.[22m[39m
[39mMore information: <https://github.com/sharkdp/bat>.[22m[39m
[32m
- Print the contents of a file to the standard output:[22m[39m
[31m    bat [22m[39m[34mfile[39m[31m[22m[39m
[32m
- Concatenate several files into the target file:[22m[39m
[31m    bat [22m[39m[34mfile1[39m[31m [22m[39m[34mfile2[39m[31m > [22m[39m[34mtarget_file[39m[31m[22m[39m
[32m
- Append several files into the target file:[22m[39m
[31m    bat [22m[39m[34mfile1[39m[31m [22m[39m[34mfile2[39m[31m >> [22m[39m[34mtarget_file[39m[31m[22m[39m
[32m
- Number all output lines:[22m[39m
[31m    bat -n [22m[39m[34mfile[39m[31m[22m[39m
[32m
- Syntax highlight a json file:[22m[39m
[31m    bat --language json [22m[39m[34mfile.json[39m[31m[22m[39m
[32m
- Display all supported languages:[22m[39m
[31m    bat --list-languages[22m[39m

[1m[39mexa
[22m[39m
[39mA modern replacement for `ls` (List directory contents).[22m[39m
[39mMore information: <https://the.exa.website>.[22m[39m
[32m
- List files one per line:[22m[39m
[31m    exa --oneline[22m[39m
[32m
- List all files, including hidden files:[22m[39m
[31m    exa --all[22m[39m
[32m
- Long format list (permissions, ownership, size and modification date) of all files:[22m[39m
[31m    exa --long --all[22m[39m
[32m
- List files with the largest at the top:[22m[39m
[31m    exa --reverse --sort=[22m[39m[34msize[39m[31m[22m[39m
[32m
- Display a tree of files, three levels deep:[22m[39m
[31m    exa --long --tree --level=[22m[39m[34m3[39m[31m[22m[39m
[32m
- List files sorted by modification date (oldest first):[22m[39m
[31m    exa --long --sort=[22m[39m[34mmodified[39m[31m[22m[39m
[32m
- List files with their headers, icons, and Git statuses:[22m[39m
[31m    exa --long --header --icons --git[22m[39m
[32m
- Don't list files mentioned in `.gitignore`:[22m[39m
[31m    exa --git-ignore[22m[39m

[1m[39mhttp
[22m[39m
[39mHTTPie: HTTP client, aims to be easier to use than cURL.[22m[39m
[39mMore information: <https://httpie.org>.[22m[39m
[32m
- Download a URL to a file:[22m[39m
[31m    http --download [22m[39m[34mexample.org[39m[31m[22m[39m
[32m
- Send form-encoded data:[22m[39m
[31m    http --form [22m[39m[34mexample.org[39m[31m [22m[39m[34mname='bob'[39m[31m [22m[39m[34mprofile_picture@'bob.png'[39m[31m[22m[39m
[32m
- Send JSON object:[22m[39m
[31m    http [22m[39m[34mexample.org[39m[31m [22m[39m[34mname='bob'[39m[31m[22m[39m
[32m
- Specify an HTTP method:[22m[39m
[31m    http [22m[39m[34mHEAD[39m[31m [22m[39m[34mexample.org[39m[31m[22m[39m
[32m
- Include an extra header:[22m[39m
[31m    http [22m[39m[34mexample.org[39m[31m [22m[39m[34mX-MyHeader:123[39m[31m[22m[39m
[32m
- Pass a user name and password for server authentication:[22m[39m
[31m    http --auth [22m[39m[34musername:password[39m[31m [22m[39m[34mexample.org[39m[31m[22m[39m
[32m
- Specify raw request body via stdin:[22m[39m
[31m    cat [22m[39m[34mdata.txt[39m[31m | http PUT [22m[39m[34mexample.org[39m[31m[22m[39m

[1m[39mtree
[22m[39m
[39mShow the contents of the current directory as a tree.[22m[39m
[39mMore information: <http://mama.indstate.edu/users/ice/tree/>.[22m[39m
[32m
- Print files and directories up to 'num' levels of depth (where 1 means the current directory):[22m[39m
[31m    tree -L [22m[39m[34mnum[39m[31m[22m[39m
[32m
- Print directories only:[22m[39m
[31m    tree -d[22m[39m
[32m
- Print hidden files too with colorization on:[22m[39m
[31m    tree -a -C[22m[39m
[32m
- Print the tree without indentation lines, showing the full path instead (use `-N` to not escape whitespace and special characters):[22m[39m
[31m    tree -i -f[22m[39m
[32m
- Print the size of each node next to it, in human-readable format, with directories displaying their cumulative size (as in the `du` command):[22m[39m
[31m    tree -s -h --du[22m[39m
[32m
- Print files within the tree hierarchy, using a wildcard (glob) pattern, and pruning out directories that don't contain matching files:[22m[39m
[31m    tree -P '[22m[39m[34m*.txt[39m[31m' --prune[22m[39m
[32m
- Print directories within the tree hierarchy, using the wildcard (glob) pattern, and pruning out directories that aren't ancestors of the wanted one:[22m[39m
[31m    tree -P [22m[39m[34mdirectory_name[39m[31m --matchdirs --prune[22m[39m
[32m
- Print the tree ignoring the given directories:[22m[39m
[31m    tree -I '[22m[39m[34mdirectory_name1|directory_name2[39m[31m'[22m[39m

[1m[39mtldr
[22m[39m
[39mDisplays simple help pages for command-line tools, from the tldr-pages project.[22m[39m
[39mMore information: <https://tldr.sh>.[22m[39m
[32m
- Show the tldr page for a command (hint: this is how you got here!):[22m[39m
[31m    tldr [22m[39m[34mcommand[39m[31m[22m[39m
[32m
- Show the tldr page for `cd`, overriding the default platform:[22m[39m
[31m    tldr -p [22m[39m[34mandroid|linux|osx|sunos|windows[39m[31m [22m[39m[34mcd[39m[31m[22m[39m
[32m
- Show the tldr page for a subcommand:[22m[39m
[31m    tldr [22m[39m[34mgit-checkout[39m[31m[22m[39m
[32m
- Update local pages (if the client supports caching):[22m[39m
[31m    tldr -u[22m[39m
This page doesn't exist yet!
Submit new pages here: https://github.com/tldr-pages/tldr
