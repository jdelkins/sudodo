%SUDODO(1)

# NAME

	sudodo

# SYNOPSIS

	ln -s /path/to/sudodo ~/bin/command-to-sudo
	hash -r
	command-to-sudo

# DESCRIPTION

Tired of invoking `sudo` every time you need to do a routine administrative
task? Would you prefer that a few commands be automatically invoked with sudo?
This is a straightforward solution.

Simply create a symlink to the `sudodo` script somewhere in your path, and
name that symlink after a real command that you would like to auto-invoke
with sudo.  Then, when you run the symlink, the script will run the first
instance of the named command in your path that matches, with sudo prepended to
the command.

Importantly, when you run a command, for exmaple `aptitude`, the shell will
traverse the $PATH environment variable to find the binary so named. For this
scheme to work, you have to have a symlink named `aptitude`, which points to
`sudodo`, in your $PATH before the real program. If the symlink's position in
the PATH is after the real program, it will never be inovked unless you give
the full pathname on the command line, which deafeats the benefit.

# AUTHOR

Joel D. Elkins <joel@elkins.co>


