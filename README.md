# Cmangos-Server-Scripts
Cmangos serverside scripts for backing up and running a cmangos server.

Don't laugh.  These are full of bugs but are functional.

Installation directions.  Each file has configuration that needs to be adjusted.  Especially paths.

Place bash files in /usr/bin so they are executable by just typing the command.
Place .service files in /etc/systemd/system

You must enable the files using systemctl:
sudo systemctl enable mangosd.service
sudo systemctl start mangosd.service

The same for realmd.service.

Good luck...
