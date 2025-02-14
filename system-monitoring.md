**Scenario:**

Doyin, a junior DevOps engineer, has been alerted by the monitoring system that one of the company's Linux servers is experiencing high CPU usage. This server hosts multiple critical applications, and it's essential to identify and resolve the issue promptly to maintain system performance and reliability.

**Assignment Tasks:**

1. **Identify the Process Causing High CPU Usage:**
   - Use appropriate Linux system monitoring commands to determine which process(es) are consuming excessive CPU resources.
   - Document the steps taken and the commands used to identify the problematic process(es).

2. **Analyze System Resource Utilization:**
   - Examine other system resources such as memory, disk I/O, and network usage to ensure they are within normal operating parameters.
   - List the commands used for this analysis and summarize the findings.

3. **Investigate the Identified Process:**
   - Gather detailed information about the process causing high CPU usage, including its purpose, owner, and related services.
   - Determine if the high CPU usage is expected behavior or indicative of an issue.

4. **Resolve the Issue:**
   - If the high CPU usage is due to a misbehaving process, outline the steps to mitigate the problem. This may include restarting the process, adjusting its configuration, or other appropriate actions.
   - If the issue requires escalation, describe the process for involving senior team members or other departments.

5. **Implement Monitoring and Alerts:**
   - Recommend additional monitoring or alerting configurations to detect similar issues proactively in the future.
   - Specify which metrics should be monitored and the thresholds for alerts.

**Deliverables:**

- A detailed report documenting each of the tasks above, including:
  - The commands used and their outputs.
  - Analysis and interpretation of the results.
  - Steps taken to resolve the issue.
  - Recommendations for future monitoring.

**Guidelines:**

- Use Linux system monitoring commands such as `top`, `htop`, `vmstat`, `iostat`, `netstat`, and others as appropriate.
- Ensure all actions are performed with consideration for system stability and uptime.
- Document your process thoroughly to demonstrate your troubleshooting methodology and thought process.

**Resources:**

- [Linux System Monitoring Commands and Tools](https://www.geeksforgeeks.org/linux-system-monitoring-commands-and-tools/)
- [Top 7 Linux Performance Commands for System Administrators](https://www.site24x7.com/learn/linux/top-commands-for-sysadmins.html)
- [20 Command Line Tools to Monitor Linux Performance](https://www.tecmint.com/command-line-tools-to-monitor-linux-performance/)

This assignment aims to assess your ability to utilize Linux system monitoring commands effectively to diagnose and resolve performance issues in a real-world scenario. 
---
**Scenario:**

Doyin, a junior DevOps engineer, has been alerted by the monitoring system that one of the company's Linux servers is experiencing high CPU usage. This server hosts multiple critical applications, and it's essential to identify and resolve the issue promptly to maintain system performance and reliability.

**Assignment Tasks and Solutions:**

**1. Identify the Process Causing High CPU Usage:**

*Commands and Steps:*

- **`top` Command:**
  - Open the terminal and run:
    ```
    top
    ```
  - This command provides a real-time overview of system processes, displaying CPU and memory usage.
  - Identify processes with the highest `%CPU` values.

- **`ps` Command:**
  - For a snapshot of current processes sorted by CPU usage:
    ```
    ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head
    ```
  - This command lists processes with their Process ID (PID), Parent Process ID (PPID), command, memory usage, and CPU usage, sorted by CPU consumption.

*Documentation:*

- Executed the `top` command to monitor real-time CPU usage.
- Used the `ps` command to list processes sorted by CPU usage.
- Identified that the process with PID 1234 (`example_process`) was consuming approximately 85% of the CPU.

**2. Analyze System Resource Utilization:**

*Commands and Steps:*

- **Memory Usage:**
  - Run:
    ```
    free -h
    ```
  - This command displays the total, used, and free memory in a human-readable format.

- **Disk I/O:**
  - Use:
    ```
    iostat -dx 2 3
    ```
  - This provides detailed CPU and disk I/O statistics, with updates every 2 seconds for 3 iterations.

- **Network Usage:**
  - Monitor with:
    ```
    iftop -i eth0
    ```
  - This command displays real-time network bandwidth usage on the `eth0` interface.

*Documentation:*

- Memory usage was within normal parameters, with 60% utilization.
- Disk I/O showed occasional spikes but remained generally stable.
- Network usage was nominal, with no significant anomalies detected.

**3. Investigate the Identified Process:**

*Commands and Steps:*

- **Process Details:**
  - Retrieve detailed information:
    ```
    ps -p 1234 -o pid,ppid,user,cmd,%mem,%cpu,etime
    ```
  - This command provides details about the process, including its runtime (`etime`).

- **Process Tree:**
  - View the process hierarchy:
    ```
    pstree -p 1234
    ```
  - This displays the process tree, helping identify parent and child processes.

*Documentation:*

- The process `example_process` (PID 1234) is owned by the user `appuser` and has been running for approximately 2 hours.
- It is a child process of `parent_process` (PID 5678).
- The high CPU usage is unexpected for this process, indicating a potential issue.

**4. Resolve the Issue:**

*Steps Taken:*

- **Restart the Process:**
  - Terminate the process:
    ```
    kill -9 1234
    ```
  - Restart the service associated with the process:
    ```
    systemctl restart example_service
    ```

- **Monitor Post-Restart:**
  - After restarting, monitor the process to ensure CPU usage returns to normal levels using the `top` command.

*Documentation:*

- Terminated the misbehaving process and restarted the associated service.
- Post-restart monitoring indicated that CPU usage normalized, with `example_process` maintaining around 5% CPU utilization.

**5. Implement Monitoring and Alerts:**

*Recommendations:*

- **Enhanced Monitoring:**
  - Implement `pidstat` to monitor per-process CPU usage at regular intervals:
    ```
    pidstat -u 60
    ```
  - This command reports CPU usage for processes every 60 seconds.

- **Set Up Alerts:**
  - Configure the monitoring system to trigger alerts if any process exceeds 70% CPU usage for more than 5 minutes.

*Documentation:*

- Scheduled `pidstat` to run every 60 seconds to collect per-process CPU usage data.
- Configured alerts to notify the team if any process sustains high CPU usage, enabling proactive issue resolution.

**Conclusion:**

Through systematic monitoring and analysis using Linux commands, the high CPU usage issue was identified and resolved. Implementing enhanced monitoring and alerting mechanisms will aid in proactively managing similar issues in the future. 
---
