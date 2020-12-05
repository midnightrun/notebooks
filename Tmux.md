# Tmux
Tmux is one of the tools I feel that I found too late in my career. It is one of the life savers which should be under the tool belt of anyone working day-to-day in the computer industry.

Simply put, Tmux is a Terminal Mutliplexer. That means it combines multiple terminals and displays those as just one. Which is in the beginning something similiar to a simple split in our terminal of choice but Tmux goes even further than this. Through its nature to be build upon a client <-> server architecture multiple clients can connect to those terminals or the client can detach from the terminal and come back at anytime and the processes are still running.

This was for me one huge selling point for Tmux. How often I accidently closed a terminal with an important running process and just killed it through this hasty reaction or the connection dropped while ssh'ing into a server with multiple terminals open to troubleshoot things.

The building blocks of Tmux are sessions, windows and panes and the Prefix. We will first follow a simple example of a day-to-day usage of Tmux and after this we will break down each part and discuss what just happend.

## Instructions

- run the following command in your shell `tmux new -s privat/tmux`
- a new window should pop up (don't be concerned about this now), press the *Control and the b* keys together, release them and press the colon (:) key
- your cursor just jumped to the bottom of the window (we just entered something called Command Mode and we will come back to this later), enter the text `new-windows` and press enter
- in the new window press the *Control and the b* keys together, release them and press the c key
- a new window should pop up again, start `htop` in the current window
- in the new window press the *Control and the b* keys together, release them and press the percent (%) key
- press now  *Control and b* keys together, release them and press the o key
- press now  *Control and b* keys together, release them and press the d key
- we are now back in our initial terminal, run the following command in your shell `tmux ls`
- to finish things up, run the following command in you shell `tmux kill-server`

## Prefix
When Tmux get started, that means the first session is started, the client can send commands to the server to trigger specific actions. While it is nice to issue commands into Tmux from the outside 

## Session
A session is a collection of windows. Take for example the task to opening and running your application code and simultanously looking at the tables of your database. In the Tmux universe you would simple create a session with two windows, one for your application code and the other for the database server connection.

A session can have a dedicated name. Currently I am following the pattern of `{work|privat}/$PROJECT_NAME`.

### Create a new session
To create a new session we call Tmux with the `new` command and optionally define a session name (it is also possible to define a command to trigger immediately within the new window but *be aware* of the behaviour of tmux to close the session if this initial process exists):

```
tmux new -s privat/notebook
```

This command will create a new session called `privat/notebook`.

## Windows
A window can have a name which can be changed to your needs, we will come back later to this.

## Panes
| 1 | 2 |
|---|---|
| 3 | 4 |
