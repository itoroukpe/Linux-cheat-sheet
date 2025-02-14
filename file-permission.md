**Scenario:**

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
