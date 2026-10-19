
# Linux Automated Data Backup Documentation

## Mission Overview

This activity demonstrates how Linux automation tools can be used to create a reliable backup process for application files. Using Bash scripting, important data can be compressed and stored in a separate directory. The Cron scheduler is also used to perform backups at a specified time without manually running the script every day.

The main purpose of this activity is to practice basic server automation, file protection, and scheduled maintenance in a cloud computing environment.

## Step 1: Preparing Sample Application Files

Before creating the backup system, a sample directory and text file were prepared to represent application information.

### Commands Used

```bash
mkdir app-data
echo "This is critical client data." > app-data/data.txt
```

### Explanation

The `mkdir` command creates a new folder named `app-data`, which serves as the source of the files that need protection.

The `echo` command writes sample content into `data.txt`. This file will be included when the backup script creates a compressed archive.

## Step 2: Developing the Backup Automation Script

A Bash script was created to automatically copy the application data into a compressed backup archive.

### Command Used

```bash
nano backup.sh
```

This command opens the Nano editor, where the backup instructions can be written and saved.

### Backup Script Source Code

```bash
#!/bin/bash

# Linux Application Data Backup Automation

cd /root || exit 1

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Starting application data backup..."

# Prepare the destination directory
mkdir -p "$BACKUP_DIR"

# Generate a compressed backup file
if tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"; then
    echo "Backup successfully created: backup_$TIMESTAMP.tar.gz"
else
    echo "Error: Backup operation failed."
    exit 1
fi
```

### Understanding the Script

The backup program performs several operations to ensure that the application files are stored properly.

1. **Working Directory:** The `cd /root` command moves to the location where the application files are expected to be stored.
2. **Source Location:** The `SOURCE_DIR` variable identifies the directory containing the application data.
3. **Backup Destination:** The `BACKUP_DIR` variable specifies where the generated archives will be saved.
4. **Timestamp:** The `date` command produces a unique date and time value for the archive filename.
5. **Directory Creation:** The `mkdir -p` command prepares the destination folder if it does not already exist.
6. **File Compression:** The `tar -czf` command packages the application directory into a compressed `.tar.gz` file.
7. **Execution Result:** The script displays a success message if the compression finishes correctly or an error message if the operation fails.

Using timestamps helps distinguish backup files created at different times.

## Step 3: Making the Script Executable

After saving the Bash script, execute permission must be assigned to the file.

### Command

```bash
chmod +x backup.sh
```

This command allows the script to run as an executable program.

### Running the Backup Script

```bash
./backup.sh
```

Executing this command starts the backup process and creates a compressed archive containing the sample application data.

### Checking the Backup Directory

```bash
ls -l backups/
```

This command displays the files stored in the backup directory.

A successfully generated backup should have a filename similar to:

```text
backup_20261019_140000.tar.gz
```

The actual filename depends on the date and time when the script was executed.

## Step 4: Configuring Automatic Backup Scheduling

To automate the backup process, the Linux Cron service was used.

Cron allows administrators to execute commands or scripts based on a predefined schedule.

### Opening the Cron Editor

```bash
env EDITOR=nano crontab -e
```

This command opens the current user's Cron configuration using Nano.

### Daily Backup Schedule

```cron
0 2 * * * /root/backup.sh
```

### Explanation of the Schedule

| Cron Field | Configuration | Description |
|---|---|---|
| Minute | 0 | Execute at minute zero |
| Hour | 2 | Execute at 2:00 AM |
| Day | * | Run every day |
| Month | * | Run every month |
| Weekday | * | Run on any day of the week |

With this configuration, the Linux system is instructed to execute the backup script daily at 2:00 AM based on the server's configured timezone.

**Note:** The schedule assumes that the script is saved at `/root/backup.sh` and the Cron job is installed under the root user.

### Confirming the Cron Configuration

```bash
crontab -l
```

This command displays the scheduled Cron tasks for the current user.

The backup schedule should appear in the output after it has been saved correctly.
configuration used for the daily automated backup.


## Step 5: Key Learning Outcomes

Through this laboratory activity, I learned how to:

- Create and execute Bash scripts in Linux.
- Organize application files and backup directories.
- Use variables to simplify script configuration.
- Generate compressed backup archives using the tar command.
- Apply executable permissions with chmod.
- Configure daily automated tasks using Cron.
- Verify backup files and scheduled tasks.
- Document automation procedures using Markdown.

## Conclusion

This laboratory helped me understand how automated backup systems support effective Linux server administration. By creating a Bash script and scheduling it with Cron, I learned how repetitive backup operations can be performed more efficiently.

The activity also showed the importance of keeping copies of application files to reduce the risk of data loss. Although automated backups are useful, administrators should still regularly check backup files and test the restoration process to ensure that the stored information can be recovered when needed.

Overall, this activity improved my practical knowledge of Bash scripting, task scheduling, and basic cloud infrastructure maintenance.

