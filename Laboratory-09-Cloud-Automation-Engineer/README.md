
# Laboratory 09 - Linux Cloud Automation and Backup Management

## Mission Overview

This laboratory introduces the use of automation tools in managing cloud-based systems. The activity involves developing a Bash script that creates compressed copies of important application files and configuring Linux Cron to execute the backup process automatically.

Through this mission, I practiced writing shell commands, organizing backup directories, managing script permissions, and scheduling routine server tasks. The backup system was designed to run every day at 2:00 AM, helping reduce the need for manual backup operations.

## Objectives

The objectives of this laboratory are:

1. Explore how automation improves Linux server administration.
2. Learn how to write and execute Bash scripts.
3. Practice creating and modifying files through the Linux terminal.
4. Understand how variables are used to store directory locations and date information.
5. Apply proper execution permissions to Bash script files.
6. Generate compressed backup archives using Linux commands.
7. Configure Cron to perform scheduled backup operations.
8. Verify the creation of backup files and scheduled tasks.
9. Prepare clear technical documentation using Markdown and GitHub.

## Commands Executed

### 1. Creating the Application Directory

The first step involves preparing a sample folder containing application data that will be included in the backup.

```bash
mkdir app-data
echo "This is critical client data." > app-data/data.txt
```

### 2. Creating and Executing the Backup Script

The following commands are used to write the backup script, assign executable permissions, and run the backup operation.

```bash
nano backup.sh
chmod +x backup.sh
./backup.sh
```

### 3. Checking the Generated Backup Files

After executing the script, the backup directory is inspected to confirm that compressed files were created.

```bash
ls -l backups/
```

### 4. Setting Up Automated Scheduling

The Cron utility is used to schedule the Bash script to run at a specific time.

```bash
env EDITOR=nano crontab -e
```

After saving the schedule, the configured tasks can be reviewed using:

```bash
crontab -l
```

## Cron Schedule Configuration

The following schedule was added to the Cron configuration:

```cron
0 2 * * * /root/backup.sh
```

### Schedule Explanation

| Setting | Value | Description |
|---|---|---|
| Minute | 0 | Executes at the start of the hour |
| Hour | 2 | Runs at 2:00 AM |
| Day of Month | * | Runs every day |
| Month | * | Runs every month |
| Day of Week | * | No weekday restriction |

This configuration schedules the backup script to execute automatically every day at 2:00 AM based on the Linux server's timezone.

The scheduled task assumes that `backup.sh` is stored in `/root` and that the Cron entry is configured for the root user.

## Skills Learned

Completing this activity helped me develop the following technical skills:

- **Linux Automation:** Understanding how repetitive system tasks can be performed automatically.
- **Bash Programming:** Writing basic scripts to execute multiple Linux commands.
- **Command-Line Management:** Creating directories, editing files, and navigating the terminal.
- **Script Permissions:** Using chmod to make Bash scripts executable.
- **Data Backup:** Creating backup copies of application files to support data protection.
- **File Compression:** Using the tar utility to produce compressed archives.
- **Task Scheduling:** Configuring Cron to run scripts according to a predefined schedule.
- **Server Maintenance:** Learning how automated processes can support regular system operations.
- **Technical Documentation:** Recording laboratory commands and procedures using Markdown in GitHub.

## Conclusion

Laboratory 09 helped me understand how automation can simplify daily responsibilities in cloud server administration. By combining Bash scripting and Cron scheduling, I learned how to create a system that can generate compressed application backups without requiring repeated manual commands.

This activity also improved my confidence in using the Linux terminal and managing scheduled processes. Overall, the mission provided useful experience in automation, data backup, and basic cloud infrastructure maintenance.

