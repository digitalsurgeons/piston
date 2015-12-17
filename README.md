# Piston

An opinionated tool for automating installs of ExpressionEngine from source zipballs.
This tool is not intended for downgrade or upgrade processes, as those tend to be
very complicated.

## Installation

Download the piston script and place the script somewhere in your `PATH`. By placing
it in your `PATH` you can use it from anywhere without having to copy
the script each time.

Once you have done this, you will need to modify the script's `SOURCE` variable
at the top of the script file to point to a folder on your system where you have
unzipped the ExpressionEngine installs for any given version.

## Usage

You can at any time type `piston` without arguments to see helpful hints, but in
short the process works like this.

Start by running pre with the version of ExpressionEngine and the name of the
control panel path you want:

    $ piston pre 2.10.1 somecrazycontrolpanel

After this process has completed, you will need to visit the control panel in
the browser and complete the form for first time ExpressionEngine installation
and allow the process to complete. Once it presents the message that you should
delete your install folder, you should run the post command.

    $ piston post

From here, you will need to modify the configuration in the `config` folder to
reconnect to the database for this install. We utilize
[ee-master-config](https://github.com/focuslabllc/ee-master-config) for
configuring ExpressionEngine.

Optionally, you can set up the new project with git through the `gitify`
subcommand. This process requires that the `git-flow` tool be installed and
also sets up some standard gitignoring in an experience-driven way.

    $ piston gitify

## Compatibility

Currently this script only works with ExpressionEngine 2. It may be expanded for
use with ExpressionEngine 3 in the future.
