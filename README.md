# Cmangos-Server-Scripts
Cmangos serverside scripts for backing up and running a cmangos server.

These were made for my HP DL380G6 running Ubuntu Server 16.04.5 LTS.  They should work just fine on any linux system that uses systemd.

 Don't laugh.  These are functional but not perfect.  They do NOT check for hard drive free space.  When your using cron they will keep operating until hard drive is full.  Beforwarned...


  //The scripts:

mangosdbbackup - Backup database script that can be executed anywhere.  Uses mysqldump to dump mangos, characters, and realmd databases.  Generates a sha hash and compresses the results into a neat tar.gz archive with, what core it was from, date, and time generated.  Places file where executed.

mangosbackup - Backup script that can be executed anywhere. This will take your whole cmangos installation and generate a neat tar.gz archive with, what core it was from, date, and time generated.  Places file where command was executed.

mangosdbbkcron - Backup database script that will generate a tar.gz the same as mangosdbbakup but will deposit it neatly in a directory that is labeled for month and year both on a local drive to the server and a remote NFS location.  This is nice to get the databases off your machine every day at a certain time religiously.
 

  // Installation directions for backup scripts.
1) Adjust each backup scripts configuration variables.  This is important.
2) Place bash files in /usr/bin so they are executable by just typing the command.
3) Add mangosdbbkcron to your crontab at the time and frequency you require.  This script should work if no NFS is available.


  // To control cmangos with systemd and have it automatically startup and shutdown
1) Edit both .service files and adjust for your cmangos path's
2) Place .service files in /etc/systemd/system
3) sudo systemctl enable mangosd.service
4) sudo systemctl start mangosd.service

The same for realmd.service.

Good luck...
ekg98
