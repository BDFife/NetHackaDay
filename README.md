# NetHackDaily

## Overview

This project represents a set of scripts that generate the HTML for
the netHackaDay website.

The long-term goal is to use Will's framework
[dennis](https://github.com/willkg/douglas) for this, but it needs
some extending and I'm not ready to switch over yet.

## Input and Output Files

To run, these tools use a set of input files that capture the state of
a NetHack game. The input files are generally created by hand.

### General Site Files

Files related to the site generally are kept in the root directory of
the project. 

config.py - a set of configuration parameters for the site.

### Specific Delve Files

Files for each 'adventure' are kept in a directory with the
character's name. 

[turn].nss - a 'nethack screen shot' generated by copying the
terminal.
[turn].obj - a list of object descriptions, reading right to left and
up to down across the terminal window. 
[turn].inv - the player's inventory.
[turn].str - an entertaining story discussing the adventure so far.
[turn].tip - an informative bit of advice or background about NetHack.
[name].json - a structured file that describes the list of turn
numbers and publish date for each turn. 

### Site Template

Jinja2 Template files that describe the site pages are included in the
templates subdirectory. 

At a minimum, the following pages are required:

about.html - general info about the site.
game_state.html - a page showing the game state for a given game and
turn.

### Output Files

Output files are generated in the compiled_site folder. 

### Static Files

Static files, like CSS, images, etc. are located in the 'static'
folder.

## Tools

There are two primary scripts used to generate the site. 

build_site.py generates the entire static site based on the parameters
in config.py and contents of the delve directories. 

build_post generates a game_state page when given a player name and
turn number.
