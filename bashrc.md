# About bashrc
"When Bash is invoked as an interactive login shell, or as a non-interactive shell with the --login option, it first reads and executes commands from the file /etc/profile, if that file exists. After reading that file, it looks for `~/.bash_profile`, `~/.bash_login`, and `~/.profile`, in that order, and reads and executes commands from the first one that exists and is readable. The --noprofile option may be used when the shell is started to inhibit this behavior." [1]

## Updating bashrc 
```bash
vim ~/.bashrc 
/* Make changes */
source ~/.bashrc
```
## Adding & Linking bash files 

Add another file to separate everything (because you can) add the following to `~/.bashrc`

```bash
if [ -f ~/{file_path} ]; then 
    . ~/.{file_path}
fi

```


First, `!/.bashrc
## References 
[1] https://www.gnu.org/software/bash/manual/html_node/Bash-Startup-Files.html