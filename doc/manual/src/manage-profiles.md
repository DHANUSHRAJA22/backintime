# Manage Profiles

Back in Time supports multiple backup profiles, allowing you to create different backup configurations for various purposes. Each profile can have its own settings, including different backup destinations, schedules, and file selections.

## Creating a New Profile

To create a new backup profile:

1. **Open Settings**: Launch Back in Time and click the "Settings" button in the main interface
2. **Profile Management**: Navigate to the "Profile" tab or use the profile dropdown menu
3. **Add New Profile**: Click "Add" or the "+" button to create a new profile
4. **Name Your Profile**: Enter a descriptive name (e.g., "Documents Backup", "Home Directory", "Project Files")
5. **Configure Settings**: Set up the backup destination, schedule, and include/exclude rules for this profile

### Best Practices for Profile Names
- Use descriptive names that clearly indicate the purpose
- Examples: "Daily Documents", "Weekly Full Backup", "USB Drive Backup", "Server Sync"
- Avoid generic names like "Profile1" or "Backup"

## Switching Between Profiles

To switch to a different profile:

1. **Profile Dropdown**: In the main window, locate the profile dropdown menu (usually at the top)
2. **Select Profile**: Click the dropdown and choose the desired profile from the list
3. **Automatic Loading**: The interface will automatically load the selected profile's settings and backup history

### Profile Switching Tips
- The current active profile is displayed in the main window title bar
- Each profile maintains its own backup timeline and restore points
- Switching profiles does not affect ongoing backup operations

## Editing Profile Settings

To modify an existing profile:

1. **Select Profile**: Switch to the profile you want to edit
2. **Open Settings**: Click the "Settings" button
3. **Modify Configuration**: Update any settings as needed:
   - **General**: Change profile name, backup destination
   - **Schedule**: Modify backup frequency and timing
   - **Include**: Add or remove directories to backup
   - **Exclude**: Set exclusion patterns for files/folders
   - **Auto-remove**: Configure retention policies
4. **Save Changes**: Click "OK" or "Apply" to save your modifications

## Deleting a Profile

!!! warning
    Deleting a profile will remove all its settings and backup history. This action cannot be undone.

To delete a profile:

1. **Select Profile**: Switch to the profile you want to delete (or select it from settings)
2. **Open Profile Settings**: Go to Settings → Profile tab
3. **Delete Profile**: Click "Remove" or the "-" button next to the profile name
4. **Confirm Deletion**: Confirm the action in the dialog box
5. **Automatic Switching**: Back in Time will automatically switch to another available profile

### Before Deleting a Profile
- **Backup Important Data**: Ensure you have copies of any critical backups
- **Export Settings**: Consider exporting the profile configuration if you might need it later
- **Check Dependencies**: Verify that no scheduled tasks depend on this profile

## Profile Management Best Practices

### Organization Strategies
- **Purpose-Based Profiles**: Create profiles based on what you're backing up (Documents, Photos, Code)
- **Frequency-Based Profiles**: Separate profiles for different backup schedules (Hourly, Daily, Weekly)
- **Destination-Based Profiles**: Different profiles for local drives, network storage, and external devices

### Example Profile Configurations

#### Daily Work Profile
- **Name**: "Daily Work Backup"
- **Schedule**: Every day at 6 PM
- **Include**: `/home/user/Documents`, `/home/user/Projects`
- **Destination**: Local external drive
- **Retention**: Keep 30 days of backups

#### Weekly System Profile
- **Name**: "Weekly System Backup"
- **Schedule**: Every Sunday at 2 AM
- **Include**: Entire home directory
- **Destination**: Network storage
- **Retention**: Keep 12 weeks of backups

#### USB Sync Profile
- **Name**: "USB Drive Sync"
- **Schedule**: When drive connected (udev)
- **Include**: Critical documents and photos
- **Destination**: USB drive
- **Retention**: Keep last 10 backups

## Troubleshooting Profile Issues

### Profile Not Loading
- **Check Permissions**: Ensure Back in Time has read access to the profile configuration
- **Verify Path**: Confirm the backup destination path is accessible
- **Restart Application**: Close and reopen Back in Time

### Profile Settings Reset
- **Configuration Corruption**: Profile settings may have been corrupted
- **Solution**: Recreate the profile with the same settings
- **Prevention**: Regularly export profile configurations as backups

### Multiple Profile Conflicts
- **Simultaneous Backups**: Avoid scheduling multiple profiles at the same time
- **Resource Conflicts**: Ensure different profiles don't backup overlapping directories to the same destination
- **Solution**: Stagger backup schedules by at least 30 minutes

### Profile Deletion Issues
- **Active Backups**: Cannot delete profile with running backup jobs
- **Solution**: Wait for backup completion or cancel active jobs
- **Locked Files**: Some systems may lock profile files during operation

## Advanced Profile Management

### Copying Profiles
1. Create a new profile
2. Manually copy settings from the existing profile
3. Adjust settings as needed for the new use case

### Importing/Exporting Profiles
- **Export**: Use the settings export feature to save profile configurations
- **Import**: Import saved configurations to restore or share profiles
- **Backup**: Keep exported profile files as configuration backups

### Profile Configuration Files
Profile settings are typically stored in:
- **Linux**: `~/.config/backintime/config`
- **Location**: Each profile has a numbered section in the configuration file

## Common Profile Use Cases

### Home User Scenarios
- **Personal Documents**: Daily backup of important files
- **Photo Archive**: Weekly backup of photo collections
- **System Configuration**: Monthly backup of system settings

### Professional Scenarios
- **Project Work**: Hourly backup during active development
- **Client Data**: Daily backup with long retention periods
- **System Administration**: Multiple profiles for different server configurations

### Multi-User Environments
- **Individual Profiles**: Each user maintains their own backup profiles
- **Shared Resources**: Common profiles for shared directories
- **Administrative Oversight**: Central management of backup policies

## Profile Performance Tips

- **Optimize Include/Exclude Rules**: Be specific about what to backup to improve performance
- **Schedule Wisely**: Avoid peak usage times for large backups
- **Monitor Disk Space**: Ensure adequate space for all configured profiles
- **Regular Maintenance**: Periodically review and clean up unused profiles

For more information on configuring specific backup settings within profiles, see the related documentation sections on scheduling, include/exclude rules, and backup destinations.
