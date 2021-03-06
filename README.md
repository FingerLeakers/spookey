# SpooKey

SpooKey is a keylogger written in C++ that uses kernel-level APIs
to capture keystrokes

[![Build Status](https://travis-ci.org/watersalesman/spookey.svg?branch=master)](https://travis-ci.org/watersalesman/spookey)

Overview
---

The Linux binary uses the Linux Input Subsystem kernel API to identify
keyboards located in `/dev/input/` and to translate key events. Threads
will spawn to record each keyboard found. Key events are written to a file
corresponding to the input device name. E.g., `event0.log` for
`/dev/input/event0`.

I will also eventually work on a Windows executable using the Windows API. I do
not plan on making a method of exfiltration anytime soon (at least not built in).
For the time being, this will be developed as a module of sorts to be used with
other software.

Usage
---
```
$ git clone https://github.com/watersalesman/spookey
$ cd spookey/src
$ cmake .
$ make
$ sudo ./spookey # Optionally use "--debug" flag
```

Demo
---

Capturing keystrokes from a separate process (separate tmux pane in this case):

<a href="https://asciinema.org/a/AFxCijfeYyUzpKBne2ziVWWjB" target="_blank"><img src="https://asciinema.org/a/AFxCijfeYyUzpKBne2ziVWWjB.png" width="75%" /></a>
