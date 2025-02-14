**Scenario:**

Luke, a system administrator, has noticed that the `/var` directory on his Linux server is consuming a significant amount of disk space, leading to storage issues. He needs to identify which subdirectories or files within `/var` are occupying the most space so he can take appropriate action to free up disk space.

**Assignment Tasks:**

1. **Assess Disk Usage of `/var`:**
   - Use the `du` command to display the disk usage of the `/var` directory and its immediate subdirectories in a human-readable format.
   - **Command:**
     ```bash
     du -h --max-depth=1 /var
     ```
   - **Expected Outcome:**
     A list showing the size of each subdirectory within `/var`, helping Luke identify which ones are using the most space.

2. **Identify Largest Subdirectories:**
   - Modify the previous command to sort the subdirectories by size in descending order to quickly pinpoint the largest ones.
   - **Command:**
     ```bash
     du -h --max-depth=1 /var | sort -hr
     ```
   - **Expected Outcome:**
     A sorted list from largest to smallest subdirectory, allowing Luke to focus on the biggest space consumers.

3. **Examine Disk Usage of a Specific Subdirectory:**
   - Choose one of the largest subdirectories identified (e.g., `/var/log`) and analyze its disk usage in detail.
   - **Command:**
     ```bash
     du -h /var/log
     ```
   - **Expected Outcome:**
     A detailed breakdown of disk usage within `/var/log`, showing the size of each file and subdirectory.

4. **Summarize Total Disk Usage of a Subdirectory:**
   - Provide a summary of the total disk usage for the chosen subdirectory (e.g., `/var/log`).
   - **Command:**
     ```bash
     du -sh /var/log
     ```
   - **Expected Outcome:**
     A single line output indicating the total size of `/var/log`.

5. **Compare with Overall Disk Usage:**
   - Use the `df` command to display the overall disk usage of the system in a human-readable format.
   - **Command:**
     ```bash
     df -h
     ```
   - **Expected Outcome:**
     An overview of the disk space usage across all mounted file systems, helping Luke understand how `/var`'s usage compares to total disk capacity.

**Deliverables:**

- A report detailing the commands executed, their outputs, and an analysis of the findings.
- Recommendations for potential cleanup actions based on the identified disk usage, such as archiving or deleting large log files, clearing cache directories, or compressing seldom-used files.

**Note:**

Ensure that any cleanup actions are performed cautiously, especially when dealing with system directories like `/var`. It's advisable to back up important data before making significant changes.

---

This assignment will help Luke develop proficiency in using Linux disk usage commands to monitor and manage system storage effectively. 
---
