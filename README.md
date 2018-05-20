# Stephanie Smith Untitled

Install [tmux](http://brewformulas.org/Tmux) to streamline pi commands.

## Connect to Pis

1. connect to 'pi' network
2. create 8 panes in terminal using tmux
	1. `tmux new`
	2. `ctrl` + `b` + `%` x4 (vertical split)
	3. `ctrl` + `b` + `,` x4 (horizontal split)
	4. `ctrl` + `b` + `cursor` to navigate

3. log onto each pi from terminal
	```
	ssh pi@pione.local (pitwo, etc.)
	```

## Run programs

1. Synchronize panes in tmux
	1. `ctrl` + `b` + `:`
	2. `setw synchronize-panes`

2. `cd git/sound-house/python`

3. Run sensors: `python3 oscDistance.py --hostIp {YOURIP} &`

4. Run audio: 
	```
	cd ../chuck
	chuck receiver.ck
	```

5. Run max patch on computer (not pis)

## Shutting Down the Pis

1. `ctrl`+`c` to kill chucK script
2. `sudo shutdown -h now`
3. turn off power strip

## How to kill python background processes

This could become an issue if the python process was running and not shut down. To shut down pi processes:
1. `ps aux | grep python`
2. `kill pid`

Note, the `pid` is different for each pi so you will need to toggle out of synchronized panes to do the `kill` commands.

## Other helpful commands

Reboot pi: `sudo reboot`