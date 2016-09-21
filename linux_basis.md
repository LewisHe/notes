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
- 