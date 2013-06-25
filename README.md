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
