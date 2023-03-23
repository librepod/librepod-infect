# LibrePod Infect

## What is this?
A script to install LibrePod on non-NixOS hosts.

This is a fork of the awesome [nixos-infect](https://github.com/elitak/nixos-infect)
script with just minor changes to install LibrePod configuration files.


## How can I use it?

1. Deploy an SSH key for the `root` user to the host where you want LibrePod be
   installed.
2. Make sure that you can connect via SSH as `root` user to that host.
3. Having SSH-ed to your host as `root` user, execute:

🧨 **WARNING!** This script WIPES OUT the targeted host's root filesystem when it runs
to completion. Any errors halt execution.

⚠ If your host supports disk snapshots, make a snapshot before running the following
command. Otherwise you won't be able to restore to the previous state. 🫵 You've
been warned!

```sh
  curl https://raw.githubusercontent.com/librepod/nixos-infect/master/nixos-infect | NIX_CHANNEL=nixos-22.11 bash -x
```

When the script succeed, the host will be rebooted. After the reboot you may either
SSH to your host with user `root` and password `librepod`, or better open your
host IP in web browser (for example http://192.168.2.2).
