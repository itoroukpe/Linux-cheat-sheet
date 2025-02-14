# Linux-cheat-sheet

Here’s a comprehensive **Linux Commands Cheat Sheet** in tabular format, with examples for each command.

---

### **Linux Commands Cheat Sheet**

| **Category**     | **Command**              | **Description** | **Example** |
|-----------------|-------------------------|----------------|-------------|
| **[File Management](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/file-management.md)** | `ls` | List files and directories | `ls -la` (List all with details) |
| | `cd` | Change directory | `cd /home/user` |
| | `pwd` | Print current directory | `pwd` |
| | `mkdir` | Create a new directory | `mkdir new_folder` |
| | `rmdir` | Remove empty directory | `rmdir old_folder` |
| | `rm` | Remove files or directories | `rm -r mydir` (Remove directory recursively) |
| | `cp` | Copy files and directories | `cp file1.txt /backup/` |
| | `mv` | Move/Rename files | `mv oldname.txt newname.txt` |
| | `touch` | Create an empty file | `touch newfile.txt` |
| | `find` | Search for files | `find /home -name "*.txt"` |
| | `locate` | Find files using a database | `locate index.html` |
| | `stat` | Display detailed information about a file | `stat myfile.txt` |
| **[File Permissions](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/file-permission.md)** | `chmod` | Change file permissions | `chmod 755 script.sh` |
| | `chown` | Change file ownership | `chown user:group file.txt` |
| | `chgrp` | Change group ownership | `chgrp developers file.txt` |
| **[File Viewing](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/file-viewing.md)** | `cat` | View contents of a file | `cat file.txt` |
| | `tac` | View contents in reverse order | `tac file.txt` |
| | `less` | View file page by page | `less longfile.txt` |
| | `head` | Display first 10 lines | `head file.txt` |
| | `tail` | Display last 10 lines | `tail file.txt` |
| | `diff` | Compare two files | `diff file1.txt file2.txt` |
| **[Process Management](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/process-management.md)** | `ps` | Show running processes | `ps aux` |
| | `top` | Display live system processes | `top` |
| | `htop` | Interactive process viewer (if installed) | `htop` |
| | `kill` | Kill a process by PID | `kill 1234` |
| | `pkill` | Kill process by name | `pkill firefox` |
| | `bg` | Resume a suspended process in the background | `bg %1` |
| | `fg` | Bring background process to foreground | `fg %1` |
| **[Disk Usage](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/disk-usage.md)** | `df` | Show disk usage | `df -h` (Human-readable) |
| | `du` | Show directory size | `du -sh /home/user` |
| | `mount` | Mount a filesystem | `mount /dev/sdb1 /mnt/usb` |
| | `umount` | Unmount a filesystem | `umount /mnt/usb` |
| **[Networking](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/networking.md)** | `ip a` | Display IP address | `ip a` |
| | `ifconfig` | Show network interfaces (deprecated) | `ifconfig eth0` |
| | `ping` | Test network connectivity | `ping google.com` |
| | `wget` | Download a file | `wget http://example.com/file.zip` |
| | `curl` | Fetch data from a URL | `curl -O http://example.com/file.zip` |
| | `netstat` | Show network connections | `netstat -tulnp` |
| | `ss` | Show active network connections | `ss -tulnp` |
| | `scp` | Securely copy files over SSH | `scp file.txt user@server:/path/` |
| | `rsync` | Sync files and directories | `rsync -av /source/ /destination/` |
| **[User Management](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/user-management.md)** | `whoami` | Show current user | `whoami` |
| | `who` | Show logged-in users | `who` |
| | `id` | Show user ID and group ID | `id username` |
| | `adduser` | Add a new user | `adduser newuser` |
| | `passwd` | Change user password | `passwd username` |
| | `usermod` | Modify a user | `usermod -aG sudo username` |
| | `deluser` | Delete a user | `deluser username` |
| | `groups` | Show user groups | `groups username` |
| **[Archiving & Compression](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/archiving-n-compression.md)** | `tar` | Archive files | `tar -cvf archive.tar files/` |
| | `tar` | Extract archive | `tar -xvf archive.tar` |
| | `gzip` | Compress file | `gzip file.txt` |
| | `gunzip` | Decompress file | `gunzip file.txt.gz` |
| | `zip` | Compress into .zip | `zip archive.zip file1 file2` |
| | `unzip` | Extract .zip file | `unzip archive.zip` |
| **[Package Management](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/package-management.md)** | `apt` | Manage Debian-based packages | `apt install package` |
| | `yum` | Manage RHEL-based packages | `yum install package` |
| | `dnf` | Modern RHEL package manager | `dnf install package` |
| | `rpm` | Install RPM package | `rpm -ivh package.rpm` |
| **[System Monitoring](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/system-monitoring.md)** | `uptime` | Show system uptime | `uptime` |
| | `free` | Show memory usage | `free -h` |
| | `vmstat` | Show system performance stats | `vmstat 5` |
| | `iostat` | Show CPU & disk I/O stats | `iostat` |
| | `dmesg` | Show system boot messages | `dmesg | less` |
| | `journalctl` | View system logs | `journalctl -xe` |
| **[Job Scheduling](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/job-scheduling.md)** | `cron` | Schedule recurring tasks | `crontab -e` |
| | `crontab -l` | List scheduled cron jobs | `crontab -l` |
| | `at` | Schedule a one-time job | `echo "ls -l" | at 10:30` |
| **[File Searching](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/file-searching.md)** | `grep` | Search for text in files | `grep "error" logfile.log` |
| | `sed` | Stream editor for modifying text | `sed 's/old/new/g' file.txt` |
| | `awk` | Process and analyze text files | `awk '{print $1}' file.txt` |
| **[Shutdown & Reboot](https://github.com/itoroukpe/Linux-cheat-sheet/blob/main/shutdown-n-reboot.md)** | `shutdown` | Shut down system | `shutdown -h now` |
| | `reboot` | Reboot system | `reboot` |
| | `halt` | Halt system | `halt` |
| | `poweroff` | Power off system | `poweroff` |

---

This **Linux Commands Cheat Sheet** provides quick access to essential commands, making it easy to reference for system administration, development, and troubleshooting.
---
