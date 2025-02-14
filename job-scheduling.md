**Scenario: Automating Log File Management with Linux Job Scheduling**

**Background:**

Okon is a system administrator responsible for maintaining a web server that generates extensive log files daily. To ensure optimal server performance and efficient storage utilization, it's crucial to manage these log files effectively. Okon aims to automate the following tasks:

1. **Log Rotation:** Archive and compress log files at the end of each day to prevent them from growing too large.
2. **Log Cleanup:** Delete archived log files older than 30 days to free up disk space.

**Tasks:**

1. **Automate Log Rotation:**
   - **Objective:** Schedule a job to archive and compress the current day's log file (`/var/log/webserver.log`) at midnight every day. The archived log should be saved with a filename that includes the date (e.g., `webserver-YYYY-MM-DD.log.gz`).
   - **Instructions:**
     - Write a shell script named `rotate_logs.sh` that performs the following actions:
       - Moves `/var/log/webserver.log` to `/var/log/archives/` with a filename appended by the current date.
       - Compresses the moved log file using `gzip`.
       - Creates a new empty `/var/log/webserver.log` file.
     - Schedule this script to run daily at midnight using the `cron` utility.

2. **Automate Log Cleanup:**
   - **Objective:** Schedule a job to delete archived log files older than 30 days from the `/var/log/archives/` directory.
   - **Instructions:**
     - Write a shell script named `cleanup_logs.sh` that deletes files in `/var/log/archives/` older than 30 days.
     - Schedule this script to run weekly on Sundays at 1:00 AM using `cron`.

**Deliverables:**

- The `rotate_logs.sh` and `cleanup_logs.sh` scripts with appropriate comments explaining each step.
- The `crontab` entries used to schedule these scripts.
- A brief explanation of how the `cron` scheduling works for these tasks.

**Considerations:**

- Ensure that the scripts have the necessary permissions to execute and perform file operations.
- Test the scripts to verify they perform the intended actions correctly before scheduling them with `cron`.
- Use absolute paths in the scripts to avoid issues with `cron` not recognizing relative paths.

**Resources:**

- [How to Schedule Tasks Using at Command in Linux](https://www.geeksforgeeks.org/how-to-schedule-tasks-using-at-command-in-linux/)
- [Job Scheduling With Unix: Best Cron Alternatives](https://www.redwood.com/article/job-scheduling-with-unix/)
- [How to Use the Linux at Command {10 Examples}](https://phoenixnap.com/kb/linux-at-command)

**Evaluation Criteria:**

- Correctness: The scripts perform the required tasks as specified.
- Efficiency: The scripts are optimized for performance and do not consume unnecessary resources.
- Clarity: The scripts and `crontab` entries are well-documented and easy to understand.
- Reliability: The scheduled tasks run consistently at the specified times without errors.

By completing this assignment, Okon will demonstrate proficiency in using Linux job scheduling commands to automate routine system maintenance tasks, a crucial skill in DevOps practices. 
---
**Solution to the Log File Management Scenario:**

**1. Automate Log Rotation:**

**Shell Script (`rotate_logs.sh`):**

```bash
#!/bin/bash

# Variables
LOG_FILE="/var/log/webserver.log"
ARCHIVE_DIR="/var/log/archives"
DATE=$(date +'%Y-%m-%d')
ARCHIVED_LOG="$ARCHIVE_DIR/webserver-$DATE.log.gz"

# Ensure the archive directory exists
mkdir -p $ARCHIVE_DIR

# Move and compress the log file
if [ -f $LOG_FILE ]; then
    mv $LOG_FILE $ARCHIVE_DIR/webserver-$DATE.log
    gzip $ARCHIVE_DIR/webserver-$DATE.log
    echo "Log file archived and compressed as $ARCHIVED_LOG"
else
    echo "Log file $LOG_FILE does not exist."
fi

# Create a new empty log file
touch $LOG_FILE
chmod 644 $LOG_FILE
echo "New log file created: $LOG_FILE"
```

*Explanation:*

- **Variables:** Define paths for the current log file, archive directory, and the archived log file with the current date.
- **Directory Check:** Ensure the archive directory exists; if not, create it.
- **Log Rotation:** If the current log file exists, move it to the archive directory with the current date appended to its name, then compress it using `gzip`.
- **Log Recreation:** Create a new empty log file with appropriate permissions for continued logging.

**Cron Job:**

To schedule the `rotate_logs.sh` script to run daily at midnight, add the following entry to the crontab:

```bash
0 0 * * * /path/to/rotate_logs.sh
```

*Explanation:*

- **`0 0 * * *`** specifies that the script runs at 00:00 (midnight) every day.
- Replace `/path/to/rotate_logs.sh` with the absolute path to the `rotate_logs.sh` script.

**2. Automate Log Cleanup:**

**Shell Script (`cleanup_logs.sh`):**

```bash
#!/bin/bash

# Variables
ARCHIVE_DIR="/var/log/archives"
DAYS_TO_KEEP=30

# Delete archived log files older than specified days
find $ARCHIVE_DIR -name "webserver-*.log.gz" -type f -mtime +$DAYS_TO_KEEP -exec rm -f {} \;
echo "Archived log files older than $DAYS_TO_KEEP days have been deleted from $ARCHIVE_DIR."
```

*Explanation:*

- **Variables:** Define the archive directory path and the number of days to retain archived logs.
- **Log Cleanup:** Use the `find` command to locate and delete compressed log files older than the specified number of days.

**Cron Job:**

To schedule the `cleanup_logs.sh` script to run weekly on Sundays at 1:00 AM, add the following entry to the crontab:

```bash
0 1 * * 0 /path/to/cleanup_logs.sh
```

*Explanation:*

- **`0 1 * * 0`** specifies that the script runs at 01:00 AM every Sunday.
- Replace `/path/to/cleanup_logs.sh` with the absolute path to the `cleanup_logs.sh` script.

**Understanding Cron Scheduling:**

The cron utility schedules tasks using a specific syntax:

```
* * * * * command_to_execute
| | | | |
| | | | └─ Day of the week (0 - 7) (Sunday=0 or 7)
| | | └─── Month (1 - 12)
| | └───── Day of the month (1 - 31)
| └─────── Hour (0 - 23)
└───────── Minute (0 - 59)
```

Each asterisk (`*`) represents a field that can be specified to determine when the command runs. For example, `0 0 * * *` means the command runs at midnight every day, while `0 1 * * 0` means it runs at 1:00 AM every Sunday. citeturn0search3

**Considerations:**

- **Permissions:** Ensure both scripts have execute permissions:

  ```bash
  chmod +x /path/to/rotate_logs.sh
  chmod +x /path/to/cleanup_logs.sh
  ```

- **Testing:** Before scheduling, test the scripts manually to confirm they work as intended.
- **Absolute Paths:** Use absolute paths in scripts and cron jobs to avoid issues with the cron environment not recognizing relative paths.

By implementing these scripts and cron jobs, Okon can automate log rotation and cleanup, ensuring efficient log management and optimal server performance. 
