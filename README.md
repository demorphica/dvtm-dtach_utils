# dvtm-dtach_utils
Wrappers for dvtm &amp; dtach to help you run persistent console sessions with your VMs with simple commands

##Install

Step 1. Install [dvtm](https://github.com/martanne/dvtm) & [dtach](https://github.com/crigler/dtach)

Step 2. Clone & install session & sconnect from this repo

```
git clone https://github.com/demorphica/dvtm-dtach_utils.git
cd dvtm-dtach_utils
sudo cp session /usr/bin/
sudo chmod +x /usr/bin/session
sudo cp sconnect /usr/bin/
chmod +x /usr/bin/sconnect
```

##Usage

###See which sessions are running

```
$ sconnect

List currently running sessions -
__________________________________
Sep 25 17:10 /tmp/console2
Oct  4 00:57 /tmp/console1
Oct  7 02:40 /tmp/console3

$
```

###Create a new console & attach to it

Running **session** *fifo_path_file* will create a session stream FIFO device on *fifo_path_file* & attach to it

```
$ session /tmp/build_console
```

List sessions again to see the new console

```
$ sconnect

Currently running sessions -
__________________________________
Sep 25 17:10 /tmp/console2
Oct  4 00:57 /tmp/console1
Oct  7 02:40 /tmp/console3
Oct  7 02:50 /tmp/build_console

$
```

###Attach to an already running console

Running **sconnect** *fifo_path_file* will connect to an existing session stream FIFO device on *fifo_path_file*

```
$ sconnect /tmp/build_console
```
