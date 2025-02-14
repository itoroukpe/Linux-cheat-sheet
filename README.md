# Linux-cheat-sheet

Here’s a comprehensive **Linux Commands Cheat Sheet** in tabular format, with examples for each command.

---

### **Linux Commands Cheat Sheet**

| **Category**     | **Command**              | **Description** | **Example** |
|-----------------|-------------------------|----------------|-------------|
| **File Management** | `ls` | List files and directories | `ls -la` (List all with details) |
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
| **File Permissions** | `chmod` | Change file permissions | `chmod 755 script.sh` |
| | `chown` | Change file ownership | `chown user:group file.txt` |
| | `chgrp` | Change group ownership | `chgrp developers file.txt` |
| **File Viewing** | `cat` | View contents of a file | `cat file.txt` |
| | `tac` | View contents in reverse order | `tac file.txt` |
| | `less` | View file page by page | `less longfile.txt` |
| | `head` | Display first 10 lines | `head file.txt` |
| | `tail` | Display last 10 lines | `tail file.txt` |
| | `diff` | Compare two files | `diff file1.txt file2.txt` |
| **Process Management** | `ps` | Show running processes | `ps aux` |
| | `top` | Display live system processes | `top` |
| | `htop` | Interactive process viewer (if installed) | `htop` |
| | `kill` | Kill a process by PID | `kill 1234` |
| | `pkill` | Kill process by name | `pkill firefox` |
| | `bg` | Resume a suspended process in the background | `bg %1` |
| | `fg` | Bring background process to foreground | `fg %1` |
| **Disk Usage** | `df` | Show disk usage | `df -h` (Human-readable) |
| | `du` | Show directory size | `du -sh /home/user` |
| | `mount` | Mount a filesystem | `mount /dev/sdb1 /mnt/usb` |
| | `umount` | Unmount a filesystem | `umount /mnt/usb` |
| **Networking** | `ip a` | Display IP address | `ip a` |
| | `ifconfig` | Show network interfaces (deprecated) | `ifconfig eth0` |
| | `ping` | Test network connectivity | `ping google.com` |
| | `wget` | Download a file | `wget http://example.com/file.zip` |
| | `curl` | Fetch data from a URL | `curl -O http://example.com/file.zip` |
| | `netstat` | Show network connections | `netstat -tulnp` |
| | `ss` | Show active network connections | `ss -tulnp` |
| | `scp` | Securely copy files over SSH | `scp file.txt user@server:/path/` |
| | `rsync` | Sync files and directories | `rsync -av /source/ /destination/` |
| **User Management** | `whoami` | Show current user | `whoami` |
| | `who` | Show logged-in users | `who` |
| | `id` | Show user ID and group ID | `id username` |
| | `adduser` | Add a new user | `adduser newuser` |
| | `passwd` | Change user password | `passwd username` |
| | `usermod` | Modify a user | `usermod -aG sudo username` |
| | `deluser` | Delete a user | `deluser username` |
| | `groups` | Show user groups | `groups username` |
| **Archiving & Compression** | `tar` | Archive files | `tar -cvf archive.tar files/` |
| | `tar` | Extract archive | `tar -xvf archive.tar` |
| | `gzip` | Compress file | `gzip file.txt` |
| | `gunzip` | Decompress file | `gunzip file.txt.gz` |
| | `zip` | Compress into .zip | `zip archive.zip file1 file2` |
| | `unzip` | Extract .zip file | `unzip archive.zip` |
| **Package Management** | `apt` | Manage Debian-based packages | `apt install package` |
| | `yum` | Manage RHEL-based packages | `yum install package` |
| | `dnf` | Modern RHEL package manager | `dnf install package` |
| | `rpm` | Install RPM package | `rpm -ivh package.rpm` |
| **System Monitoring** | `uptime` | Show system uptime | `uptime` |
| | `free` | Show memory usage | `free -h` |
| | `vmstat` | Show system performance stats | `vmstat 5` |
| | `iostat` | Show CPU & disk I/O stats | `iostat` |
| | `dmesg` | Show system boot messages | `dmesg | less` |
| | `journalctl` | View system logs | `journalctl -xe` |
| **Job Scheduling** | `cron` | Schedule recurring tasks | `crontab -e` |
| | `crontab -l` | List scheduled cron jobs | `crontab -l` |
| | `at` | Schedule a one-time job | `echo "ls -l" | at 10:30` |
| **File Searching** | `grep` | Search for text in files | `grep "error" logfile.log` |
| | `sed` | Stream editor for modifying text | `sed 's/old/new/g' file.txt` |
| | `awk` | Process and analyze text files | `awk '{print $1}' file.txt` |
| **Shutdown & Reboot** | `shutdown` | Shut down system | `shutdown -h now` |
| | `reboot` | Reboot system | `reboot` |
| | `halt` | Halt system | `halt` |
| | `poweroff` | Power off system | `poweroff` |

---

This **Linux Commands Cheat Sheet** provides quick access to essential commands, making it easy to reference for system administration, development, and troubleshooting.
---
**Scenario: Organizing Project Files with Linux File Management Commands**

**Background:**

Alice is a DevOps engineer working on a new project. She needs to set up a structured directory environment to organize her project files efficiently. This involves creating directories, navigating through them, managing files, and setting appropriate permissions using Linux commands.

**Tasks:**

1. **Navigate to the Home Directory:**
   - Alice should start by ensuring she is in her home directory.
   - **Command:** `cd ~`

2. **Create a Project Directory Structure:**
   - Within her home directory, Alice needs to create the following directory hierarchy:
     ```
     project/
     ├── src/
     ├── docs/
     └── tests/
     ```
   - **Commands:**
     - `mkdir project`
     - `cd project`
     - `mkdir src docs tests`

3. **Create Empty Files:**
   - In the `src` directory, Alice should create three empty files: `main.py`, `utils.py`, and `config.py`.
   - **Commands:**
     - `cd src`
     - `touch main.py utils.py config.py`

4. **List Files with Detailed Information:**
   - Alice wants to view the files in the `src` directory with detailed information, including permissions, ownership, size, and modification date.
   - **Command:** `ls -l`

5. **Set Permissions:**
   - Alice needs to ensure that only she can read and write the files in the `src` directory, while others should have no access.
   - **Command:** `chmod 600 *.py`

6. **Move Files:**
   - Alice decides to move `config.py` from the `src` directory to the `docs` directory for better organization.
   - **Commands:**
     - `mv config.py ../docs/`
     - `cd ../docs`
     - `ls` (to verify the file has been moved)

7. **Copy Files:**
   - Alice wants to create a backup of `main.py` in the `tests` directory.
   - **Command:** `cp ../src/main.py ../tests/main_backup.py`

8. **Remove a File:**
   - After reviewing, Alice decides to delete `utils.py` from the `src` directory.
   - **Command:** `rm ../src/utils.py`

9. **Display File Content:**
   - Alice wants to quickly view the content of `main_backup.py` without opening an editor.
   - **Command:** `cat ../tests/main_backup.py`

10. **Clean Up:**
    - After completing her tasks, Alice decides to remove the entire `project` directory and its contents.
    - **Command:** `cd ~`
    - **Command:** `rm -r project`

**Objective:**

Through this scenario, Alice will demonstrate proficiency in essential Linux file management commands, including `cd`, `mkdir`, `touch`, `ls`, `chmod`, `mv`, `cp`, `rm`, and `cat`. These commands are fundamental for efficient file and directory management in a Linux environment.

**Note:**
```
It's crucial to execute these commands carefully, especially those that modify or delete files and directories. Always ensure you're operating in the correct directory and that you have backups of important data before performing operations that cannot be undone.
```
---
**Scenario: File Permission**

Melinda is a system administrator at a company where multiple users collaborate on various projects. Each project has its own directory, and team members need appropriate access to these directories to perform their tasks efficiently. Recently, Melinda noticed that some users inadvertently modified or deleted files they shouldn't have, leading to data inconsistencies and workflow disruptions. To prevent such issues, Melinda decides to implement stricter file permission controls using Linux commands.

**Tasks:**

1. **Directory Setup:**
   - Create a directory named `project_alpha` in the `/home/projects` path.
   - Within `project_alpha`, create two subdirectories: `docs` and `scripts`.

2. **User and Group Management:**
   - Create a user group named `alpha_team`.
   - Add users `alice`, `bob`, and `charlie` to the `alpha_team` group.

3. **Ownership Assignment:**
   - Set the owner of the `project_alpha` directory and its subdirectories to `melinda`.
   - Set the group ownership of these directories to `alpha_team`.

4. **Permission Configuration:**
   - For the `project_alpha` directory:
     - Grant the owner full permissions.
     - Grant the group read, write, and execute permissions.
     - Deny all permissions to others.
   - For the `docs` subdirectory:
     - Ensure that files created within inherit the `alpha_team` group ownership.
     - Prevent users from deleting or renaming files they don't own.
   - For the `scripts` subdirectory:
     - Allow users to read and execute scripts but restrict modifications.

5. **Verification:**
   - As user `alice`, create a file named `overview.txt` in the `docs` directory.
   - As user `bob`, attempt to delete `overview.txt`.
   - As user `charlie`, create a script named `deploy.sh` in the `scripts` directory and attempt to execute it.

**Expected Outcomes:**

- Users in the `alpha_team` group can collaborate within the `project_alpha` directory without interfering with each other's work.
- Files in the `docs` directory inherit the `alpha_team` group ownership, and only the file owner or `melinda` can delete or rename them.
- Scripts in the `scripts` directory can be executed by all group members, but only modified by the owner or `melinda`.

**Guidelines:**

- Use the `chmod` command to modify file and directory permissions.
- Use the `chown` command to change file and directory ownership.
- Use the `chgrp` command to change group ownership.
- Apply the `setgid` bit where necessary to ensure new files inherit the correct group ownership.
- Apply the `sticky` bit where necessary to restrict file deletion or renaming.

**Submission:**

Document the commands used for each task and provide a brief explanation of their purpose. Include the output of relevant commands (e.g., `ls -l`) to demonstrate the final permission settings. Discuss any challenges encountered and how they were addressed.

**References:**

- [Linux File Permissions Explained](https://www.redhat.com/en/blog/linux-file-permissions-explained)
- [Understanding Linux File Permissions](https://www.linuxfoundation.org/blog/blog/classic-sysadmin-understanding-linux-file-permissions)
- [Setuid, Setgid, and Sticky Bits](https://en.wikipedia.org/wiki/Setuid)
```
*Note: Ensure that all commands are tested in a safe environment to prevent unintended system changes.*
```
---
**Answers to File Permission Assignment**
To address the scenario where Melinda needs to manage file permissions for collaborative projects, here are the detailed steps and commands to achieve the desired configuration:

**1. Directory Setup:**

- **Create the main project directory and subdirectories:**

  ```bash
  sudo mkdir -p /home/projects/project_alpha/{docs,scripts}
  ```

  *Explanation:* The `mkdir -p` command creates the `project_alpha` directory along with its `docs` and `scripts` subdirectories. The `-p` flag ensures that parent directories are created as needed.

**2. User and Group Management:**

- **Create the `alpha_team` group:**

  ```bash
  sudo groupadd alpha_team
  ```

- **Add users to the `alpha_team` group:**

  ```bash
  sudo usermod -aG alpha_team alice
  sudo usermod -aG alpha_team bob
  sudo usermod -aG alpha_team charlie
  ```

  *Explanation:* The `groupadd` command creates a new group named `alpha_team`. The `usermod -aG` command appends (`-a`) each user to the specified group (`-G`).

**3. Ownership Assignment:**

- **Set ownership of the directories:**

  ```bash
  sudo chown -R melinda:alpha_team /home/projects/project_alpha
  ```

  *Explanation:* The `chown -R` command changes the ownership of the `project_alpha` directory and all its contents recursively (`-R`) to user `melinda` and group `alpha_team`.

**4. Permission Configuration:**

- **Set permissions for the `project_alpha` directory:**

  ```bash
  sudo chmod 770 /home/projects/project_alpha
  ```

  *Explanation:* The `chmod 770` command sets the permissions so that the owner (`melinda`) and group (`alpha_team`) have full read (`r`), write (`w`), and execute (`x`) permissions, while others have no permissions.

- **Configure the `docs` subdirectory:**

  ```bash
  sudo chmod 2770 /home/projects/project_alpha/docs
  sudo chmod +t /home/projects/project_alpha/docs
  ```

  *Explanation:* The `chmod 2770` command sets the setgid bit (`2`) on the `docs` directory, ensuring that new files inherit the `alpha_team` group ownership. The `chmod +t` command adds the sticky bit, preventing users from deleting or renaming files they don't own.

- **Configure the `scripts` subdirectory:**

  ```bash
  sudo chmod 2775 /home/projects/project_alpha/scripts
  ```

  *Explanation:* The `chmod 2775` command sets the setgid bit (`2`) on the `scripts` directory, ensuring new files inherit the `alpha_team` group ownership. The permissions `775` allow the owner and group to read, write, and execute, while others can read and execute.

**5. Verification:**

- **As user `alice`, create a file in the `docs` directory:**

  ```bash
  sudo -u alice touch /home/projects/project_alpha/docs/overview.txt
  ```

- **As user `bob`, attempt to delete `overview.txt`:**

  ```bash
  sudo -u bob rm /home/projects/project_alpha/docs/overview.txt
  ```

  *Expected Outcome:* Bob should receive a "Permission denied" error due to the sticky bit, which restricts file deletion to the file owner and directory owner.

- **As user `charlie`, create and execute a script in the `scripts` directory:**

  ```bash
  sudo -u charlie bash -c 'echo -e "#!/bin/bash\necho Hello, World!" > /home/projects/project_alpha/scripts/deploy.sh'
  sudo -u charlie chmod +x /home/projects/project_alpha/scripts/deploy.sh
  sudo -u charlie /home/projects/project_alpha/scripts/deploy.sh
  ```

  *Expected Outcome:* Charlie should be able to create, modify, and execute the `deploy.sh` script within the `scripts` directory.

**Final Verification:**

- **List the directories with detailed permissions:**

  ```bash
  ls -ld /home/projects/project_alpha
  ls -ld /home/projects/project_alpha/docs
  ls -ld /home/projects/project_alpha/scripts
  ```

  *Expected Output:*

  ```
  drwxrwx--- 3 melinda alpha_team 4096 Feb 18 12:00 /home/projects/project_alpha
  drwxrws--T 2 melinda alpha_team 4096 Feb 18 12:00 /home/projects/project_alpha/docs
  drwxrwsr-x 2 melinda alpha_team 4096 Feb 18 12:00 /home/projects/project_alpha/scripts
  ```

  *Explanation:* The `s` in the group permissions indicates the setgid bit is set, and the `T` indicates the sticky bit is set without execute permission for others.

**Discussion:**

By setting these permissions and ownerships, Melinda ensures that:

- All members of the `alpha_team` can collaborate within the `project_alpha` directory.

- Files in the `docs` directory inherit the `alpha_team` group ownership, and only the file owner or `melinda` can delete or rename them, thanks to the sticky bit.

- In the `scripts` directory, scripts can be executed by all group members, but only modified by the owner or `melinda`.

This configuration minimizes accidental modifications or deletions, maintaining data integrity and workflow efficiency.
```
*Note:* Ensure that all commands are executed with appropriate privileges, and always verify the effects of permission changes in a controlled environment before applying them to production systems.
```
---



















---
**Scenario: Package Management**

John is working on a Linux-based project that requires the use of specific file management tools. He needs to perform various tasks such as searching for files, compressing directories, and monitoring disk usage. However, he discovers that some of the necessary utilities are not installed on his system. To resolve this, John decides to use Linux package management commands to install the required tools.

**Assignment Tasks:**

1. **Identify Missing Utilities:**
   - Determine which file management utilities are not currently installed on John's system but are needed for his project. List at least three such utilities and explain their primary functions.

2. **Install Missing Utilities:**
   - Using the appropriate package management commands for John's Linux distribution, install the identified utilities. Provide the exact commands used for installation.

3. **Verify Installation:**
   - After installation, verify that each utility is correctly installed and functioning. Describe the steps taken to confirm their proper installation.

4. **Update System Packages:**
   - Ensure that all installed packages on John's system are up-to-date. Use the package manager to update the system and list the commands executed.

5. **Remove Unnecessary Packages:**
   - Identify any obsolete or unnecessary packages on John's system. Use package management commands to remove these packages and clean up the system. Document the commands used and the rationale for removing specific packages.

**Guidelines:**

- Clearly state any assumptions made about John's Linux distribution.
- Provide detailed explanations for each step to demonstrate your understanding of Linux package management.
- Include any relevant options or flags used in the commands and explain their purposes.
- Ensure that all commands are appropriate for the assumed Linux distribution and version.
```
**Note:** This assignment aims to assess your proficiency in using Linux package management tools to manage software installations, updates, and removals effectively.
```
---

**Answer to Package Management**

For this scenario, we'll assume John is using a Debian-based Linux distribution, such as Ubuntu. The package management commands provided will be specific to APT, the package manager used in Debian-based systems.

**1. Identify Missing Utilities:**

John needs the following file management utilities for his project:

- **`locate`**: A utility to quickly find the location of files on the system by searching a pre-built database.
- **`zip`**: A compression utility to package and compress files and directories into `.zip` archives.
- **`ncdu`**: A disk usage analyzer with a text-based user interface, useful for tracking disk space usage.

**2. Install Missing Utilities:**

To install these utilities, John can use the following commands:

```bash
sudo apt update
sudo apt install mlocate zip ncdu
```

**Explanation:**

- `sudo apt update`: Updates the package list to ensure the latest versions are available.
- `sudo apt install mlocate zip ncdu`: Installs the `mlocate` (which provides the `locate` command), `zip`, and `ncdu` packages.

**3. Verify Installation:**

After installation, John can verify that each utility is installed and functioning:

- **`locate`**:

  ```bash
  locate --version
  ```

  This command should display the version of `locate` installed, confirming its availability.

- **`zip`**:

  ```bash
  zip --version
  ```

  This command will display the version of `zip` installed.

- **`ncdu`**:

  ```bash
  ncdu --version
  ```

  This command will display the version of `ncdu` installed.

**4. Update System Packages:**

To ensure all installed packages are up-to-date, John can execute:

```bash
sudo apt update
sudo apt upgrade
```

**Explanation:**

- `sudo apt update`: Refreshes the package list.
- `sudo apt upgrade`: Upgrades all installed packages to their latest versions.

**5. Remove Unnecessary Packages:**

To clean up unnecessary packages and dependencies, John can use:

```bash
sudo apt autoremove
sudo apt clean
```

**Explanation:**

- `sudo apt autoremove`: Removes packages that were automatically installed to satisfy dependencies for other packages and are no longer needed.
- `sudo apt clean`: Clears out the local repository of retrieved package files, freeing up disk space.

**Note:** It's essential to exercise caution when removing packages to avoid unintentionally deleting essential components.

By following these steps, John can effectively manage the installation, verification, updating, and removal of packages using APT on a Debian-based system. 
---
