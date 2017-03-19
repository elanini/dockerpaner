# dockerpaner
automatically open new docker container logs in a new pane of iTerm2

It's not perfect but it works, and well enough for 128

## Installation
Just pop the file wherever, make it executable, and run it
you may need to change the docker path at the top
```
./dockerpaner.jxa
```
this assumes that iTerm2 is installed and running on a mac (10.10+? maybe lower maybe higher).

## usage
the script accepts two arguments, -c and -k. you cant do -ck. just -c and or -k. 

-c : a window is opened at the start of the script that we can split from. -c closes this pane once it is split off of

-k : by default the docker logs command is run directly, bypassing the shell. this command lets the shell open and then writes and runs the docker logs command, so that if a container crashes the pane does not close. 

## how it works
check for new containers every 3 seconds

split the rightmost panes from top to bottom inserting the new docker logs command

## limitations
the script will continue to work if one of the original panes is still open, but if
you close the whole window it will crash. you can just restart it. 
