**Scenario:**

Grace is a system administrator at a mid-sized company that uses a Linux-based server environment. Recently, the company hired a new developer, Alex, who needs access to the development server to work on a project. Grace's task is to set up Alex's user account with the appropriate permissions and ensure that security protocols are maintained.

**Tasks:**

1. **Create a New User Account:**
   - Grace needs to create a user account for Alex with the username `alex`. The account should have a home directory and use `/bin/bash` as the default shell.

2. **Set a Password for the New User:**
   - After creating the account, Grace must set a secure password for Alex.

3. **Add the User to a Group:**
   - Alex will be part of the `developers` group, which has specific permissions for project directories. Grace needs to add Alex to this group.

4. **Verify User and Group Configuration:**
   - Grace should confirm that Alex's account has been set up correctly and that he is a member of the `developers` group.

5. **Set Account Expiration:**
   - Since Alex is a contractor, his account should expire in 90 days. Grace needs to configure the account to automatically disable after this period.

6. **Implement Security Measures:**
   - To enhance security, Grace should ensure that Alex is required to change his password upon first login.

**Instructions:**

For each task, provide the specific Linux commands Grace should use, along with a brief explanation of what each command does. Ensure that the commands are appropriate for a typical Linux distribution and consider best practices for user management and security.

**Expected Deliverables:**

- A list of commands for each task.
- A brief explanation of each command's purpose and function.
- Any additional considerations or best practices that Grace should be aware of when performing these tasks.

**Note:**

This assignment aims to assess your understanding of Linux user management commands and your ability to apply them in practical scenarios. Ensure that your explanations are clear and concise, demonstrating a thorough grasp of the concepts involved. 
---
Here are the solutions to the tasks outlined in the scenario:

**1. Create a New User Account:**

**Command:**

```bash
sudo useradd -m -s /bin/bash alex
```

**Explanation:**

- `sudo`: Executes the command with administrative privileges.
- `useradd`: Creates a new user account.
- `-m`: Creates a home directory for the user at `/home/alex`.
- `-s /bin/bash`: Sets `/bin/bash` as the default login shell for Alex.
- `alex`: Specifies the username.

This command creates a new user named Alex with a home directory and sets the default shell to Bash.

**2. Set a Password for the New User:**

**Command:**

```bash
sudo passwd alex
```

**Explanation:**

- `passwd`: Changes the password for a user account.
- `alex`: Specifies the username.

After executing this command, you'll be prompted to enter and confirm a new password for Alex.

**3. Add the User to a Group:**

**Command:**

```bash
sudo usermod -aG developers alex
```

**Explanation:**

- `usermod`: Modifies an existing user account.
- `-aG developers`: Appends (`-a`) Alex to the `developers` group (`-G`).
- `alex`: Specifies the username.

This command adds Alex to the `developers` group without affecting his membership in other groups.

**4. Verify User and Group Configuration:**

**Commands:**

```bash
id alex
```

**Explanation:**

- `id`: Displays user identity information, including UID (User ID), GID (Group ID), and group memberships.
- `alex`: Specifies the username.

This command confirms that Alex's account is set up correctly and that he is a member of the `developers` group.

**5. Set Account Expiration:**

**Command:**

```bash
sudo chage -E $(date -d "+90 days" +%Y-%m-%d) alex
```

**Explanation:**

- `chage`: Changes user account expiration information.
- `-E $(date -d "+90 days" +%Y-%m-%d)`: Sets the account to expire 90 days from today.
- `alex`: Specifies the username.

This command configures Alex's account to automatically disable after 90 days.

**6. Implement Security Measures:**

**Command:**

```bash
sudo chage -d 0 alex
```

**Explanation:**

- `chage`: Changes user account expiration information.
- `-d 0`: Sets the last password change date to 0, forcing a password change on next login.
- `alex`: Specifies the username.

This command ensures that Alex is required to change his password upon first login.

**Additional Considerations:**

- **Password Policies:** Implement strong password policies to enhance security.
- **Account Monitoring:** Regularly monitor user accounts and group memberships to ensure compliance with security protocols.
- **Documentation:** Maintain clear documentation of user account configurations and changes for auditing purposes.

By following these steps, Grace can effectively manage user accounts and maintain system security. 
