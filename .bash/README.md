-----------------------------------------------
- This is the Baby-GNU bash init files. -
-----------------------------------------------

    bash initialisation system
    Copyright (C) 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011  Daniel Dehennin <daniel.dehennin@baby-gnu.org>

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.


- What is it ?
==============

This is my own init file for bash on my Debian GNU/Linux Sarge.
I make the possible to use it on non Debian system in including the
bash_completion of my system (for those who have not this feature).

I think that bash >= 2.0.4 is needed (for completion)

I began to make my own init script with the advanced bash scripting guide
available in the linux document project (http://www.tldp.org)


- How to install it ?
=====================

Make a bakup of all you .bash*, I use this regex to make the archive :

 $ tar cf - .bash* | gzip -9c > init_bash_nebu.tar.gz

so all directly under you home directory can be overwritten.
Then simply unzip and untar it in your home directory :

 $ gzip -dc init_bash_nebu.tar.gz | tar -xvf-

- Why a so complexe structure ?
===============================

This init setting is intended to correspond to the maximum need of people.
It make the distinction beetween interactie and non interactive mode :

-> interactive mode is the common use for people, you give bash some command to
   execute, it executes it (successfully or not but it does it) and it gives you
   the result.

-> non interactive mode is the mode for scripts executed on the command line of
   by cron or others.

You can test the little scripts in the subdir test of the .bash/, the main
script is interactivity which calls the two other scripts test_interactive and
test_non_interactive but you can test them separately.


- And my personal settings ?
============================

If you want to add more stuff in the init section for your bash (fully
recommnded to automate things) you can put it in only one directory :

-> if it's only for interactive shell or script (wich interact with the user),
   put it in ~/.bash/rc.interactive/

-> if it's only for non interactive shell or script (typically cron script), put
   it in ~/.bash/rc.non_interactive/

-> if it's for both interactive and non interactive (e.g. you want to add your
   ~/bin directory in the PATH variable), put it in ~/.bash/rc/.


in all that directory you have the same structure :

-> 1_bash.rc : loaded first beceause of the "1", you can put needed
   absolutely_first_load stuff (definition of a function used everywhere).

-> different files corresponding to one need loaded in alphabetical order (take
   care of that when you add dependency in function calls for exemple.


- Can I contribute ?
====================

If you want to see your contributions added in my very little contribution to the
community, feel free to send me a mail, I will include it with pleasure.
