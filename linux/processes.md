# Processes
A process is any program that is currently running on a system. For example, opening the terminal or the browser.

There are 2 main types of processes in Linux:
- <u>Foreground Process</u>: These processes depend on the user for input, also known as interactive processes.
- <u>Background Process</u>: These processes run independently of the user, known as automatic/non-interactive processes.

Each process also has one of the following states:
- <u>Running</u>: Means that it's executing currently.
- <u>Sleeping</u>: Means it's waiting for resources to be available. A process in *interruptible* sleep will wake up to handle signals, while *uninterruptible* sleep processes will not.
- <u>Stopped</u>: Means it got a stop signal.
- <u>Zombie</u>: Means the process is finished running, but still remains in the system's process table (wasn't exited properly).

We can view processes running on our computer using two commands: top and ps aux.

## Process Commands
top launches an interactive terminal UI for us to view a continously updating list of processes happening on our computer. This makes it possible for live tracking of processes (until we quit it by pressing q).

''' Image here '''

ps aux on the other hand gives us a snapshot of processing running on our computer. In case we just want a one time result and not a live stream, ps aux is the command we're looking for.

''' Image here '''

Each process has a **PID**, which stands for Unique Process ID. Simply put, it's an ID for a process, and each process has a unique one.

Processes can be started using,  

'''bash
systemctl [option] [service]
systemctl start apache

and ended using,

'''bash
kill [service]
kill apache2

## Foregrounding & Backgrounding
As described previously, processes can run both in the fore and background. If a process were running in the foreground, we would not be able to type or execute anything else in the terminal until the process is complete. This can waste time, especially for long processes whose results we don't need anytime soon. Instead, we can background these processes so they run behind the scenes, while we continue working on other stuff.

We can see some commands that help us work with processes in the fore and background, 

''' bash
python3 script.py   // Runnning on the foreground
python3 script.py & // Running on the background
fg                  // Send most recent job to foreground (add job numbern, which is found by running jobs, to fg the exact process)
bg                  // Send current job to background





