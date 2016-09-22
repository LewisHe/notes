## Linux Basic
#### shell expansion
- command line scan and cutting it up in arguments
- white space removal
- single quote: no parsing of variables
- double quote: allow parsing of variables

### control operators
- `;` -- statement termination;
- `&` -- background process
- `$?`-- shell parameter that stores the exit code of previous process
- `&&`-- logical and
- `||`-- logical or
- `#` -- comments
- `\` -- escape chars
### variables
- `$<var_name>` -- refers to an environment variable named as `var_name`
    - case sensitive
    - set variable syntax: `<var_name>=<var_value>`
    - complete form: `${<var_name>}`
- `$PS1` -- shell prompt
- `$PATH` -- where the shell is looking for commands
    - directories seperated by `:`
    - the shell will not look in the current directory for commands to execute
- `set` : to display a list of environment variables, all variables including thoes not exported to child shells
- `unset`: to remove a variable from shell environment
- `env`: to display a list of **exported variables**, which will be inherited by child shells.
- `echo $-`: to list all the set options of current shell

### shell embedding
- dollar-bracket: $(), recommended
- backsticks: ``, but cant nest embedded shell. and it is easily confusing with ''

### shell history
- `!!`: repeat last command
- `!<chars>`: repeat command starting with <chars>
- `!<n>`: repeat the command with identifier number *n*
- `!<regexp>`, where <regexp> in the format: **<chars>:s/1/2**
- Ctrl-r : to search history
- `$HISTSIZE`, `$HISTFILE`, `$HISTFILESIZE`

### File Globbing
- `*`: any combination of chars, even none
- `?`: a single char
- `[]`: any of the chars specified inside the bracket
- `a-z`, `0-9`: chars within the range, use with `[]`
- `[!]`: any chars NOT specified inside the bracket
- `$LANG` some languages include lower case letters in an upper case range
- escaping globbing by using single quotes, or escape chars

### redirecting and pipes
- stream 0: stdin
- stream 1: stdout
- stream 2: stderr
- **stdout** can be redirected with a `>` sign
    - it is in fact the abbreviation of `1>(stdout)`
    - the output file is erased
    - erasing a file while using `>` can be prevented by setting `noclobber` option
    - `noclobber` option can be overruled by `>|`
- `>>` to append
- error redirection: `2>stderr`, `2>&1`
- input redirection `<`
- `<<` here document: is a way to append input until a certain sequence (eg *EOF*, or Ctrl-D) is encountered.
- `<<<` here string: is used to directly pass strings to a command, same as `echo string | command`, but with one less process running
- pipes: `|`: pipe from stdout of one process to stdin of another process

### filters
- `cat`
- `tee`
- `grep`
- `cut`
- `tr`
- `wc`
- `uniq`
- `sort`
- `comm`
- `od`
- `sed`

### Basic unit tools
- `find`
    - `find . -name "*.conf"`
    - `find . -type f -name "*.conf"`
    - `find . -newer test.txt`
    - `touch -t 20160130 marker_start`
    - `find . -type f -newerat "20160130 23:59:59"`
    - `find . -name "*.conf" -exec grep test {} /backup/ \;` 
        - find will execute grep and will substitute {} with the filename(s) found. The difference between ; and + is that with ; a single grep command for each file is executed whereas with + as many files as possible are given as parameters to grep at once.
    - not operator: `!`: `find . ! -name "*.conf"`
    - or operator: `-o`: `find . -name "*.conf" -o -name "*.txt"`
    - by permission: `-perm`
    - limit depth: `-maxdepth`
    - readonly file: `find . -perm /u=r`
    - by owner `-user`
    - by group `-group`
- `locate` : uese an index to locate files
- `date`
- `cal`
- `sleep`
- `time`: display how long it taks to execute a command
- `gzip`, `gunzip`
- `zcat`, `zmore`: to view zipped text files

### scripting
- `source`, `.`
- which shell runs the scripts?
    - run with `bash script`
    - specified at the first line `#!/bin/bash`
- `bash -x script` to debug






