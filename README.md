# Run tasks in a window

Sometimes you want the ability to run a (long running) commandline task in a
window without cluttering your open terminal windows (e.g. ssh tunnels). Or
you just want to start a process with a button (e.g. regularly running build
processes).

Then this script is for you:

* Tasks are startable and killable with a button
* Output is shown in the main window (autoscroll if the last line is visible)
* Tasks are defined as "name = command". Normal shell command chaining (`a && b`)
  and loops (`while true; do something; done`) are possible
* Close will minimize to the tray and not kill the running tasks
* Name, window icon and tray icon are configurable
* Config file name is derived from script name (i.e. you can separate configs
  by symbolic linking the script to a new name). Config is in `~/.config/<scriptname>.ini`
* Example config is generated on first start
* Implemented in **python3** with the **wx toolkit** under the **MIT License**

Tested under Linux. Windows & Mac should be possible but are up to now untested.

## Install

There are three dependency: `python3`, `psutil` and the python wx toolkit.

* On Debian: `sudo apt install python3-wxgtk4.0 python3-psutil`

Script is installed by putting a copy of the script into `$PATH`:

```bash
cd ~/bin # or wherever you want it...
wget https://raw.githubusercontent.com/jankatins/run_tasks_window/master/run_tasks
chmod +x run_tasks
```

Or clone the repository and link the script into the `$PATH`:
```bash
git clone https://github.com/jankatins/run_tasks_window.git
# assuming ~/bin is in $PATH
ln -s $(pwd)/run_tasks_window/run_tasks ~/bin/run_tasks
```

If you want multiple run commands with different configs:

```bash
ln -s run_tasks run_tunnels
```

## Run

```bash
run_tasks # or whatever you named it
```

## Contribute

Suggestions, patches or pull requests very welcome!

