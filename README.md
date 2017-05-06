# shell-notes
My personal notebook for all notes I come up with related to any shell script.
The `README.md` is largely miscallaneous, any other markdown documents are there because they've been named based off a category that all those notes belong to.

# Notes
## Reserved or Conventional Exit Codes
1. Catchall for general errors
2. Misuse of shell built-ins
    - these are used for bash builtins, don't define these yourself
126. Command invoked cannot execute
    - Permission problems
    - Command isn't an executable
127. "Command not found"
    - `illegal_command`
    - Possible problam with $PATH or a typo
128. Invalid argument to exit
    - ie. `exit_3.14159`
    - `exit` takes only integer args from 0 - 255
129. **128+n** Fatal error signal *n*
    - ie. `kill -1 $PPID of script`
    - returns **129** from kill -**1** **129**=(128+**1**)
130. Script terminated by Control-C
    - this is the same as kill signal **2**
    - from before exit code convention `128+n` results in this one
256. Anything higher than **255** shouldn't happen
    - Exit codes only go from 0 - 255
