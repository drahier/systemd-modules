systemd-modules
===============

Some systemd service, unit and script files.

kill-ssh-sessions
-----------------

Kills running ssh sessions before suspending, shutting down or rebooting.
This will prevent ssh clients from freezing when the server turns off.

Files needed:

- etc/systemd/system/kill-ssh-sessions.service
- etc/systemd/scripts/kill-ssh-sessions

Activate with: `systemctl enable kill-ssh-sessions`


musicbackup
-----------

Triggered by a change of the mpd database file, this will backup the entire
music collection to another server using rsync with ssh.
If the server is not online, the script will wait for some time and try again.

Files needed:

- etc/systemd/system/musicbackup.service
- etc/systemd/system/musicbackup.path
- etc/conf.d/musicbackup
- etc/systemd/scripts/rsync

Activate with: 

    systemctl enable musicbackup.path
    systemctl start musicbackup.path
