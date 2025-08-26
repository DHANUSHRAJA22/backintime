# Manage profiles
  configurable time (hours, days or weeks) when the last backup was done
  before this delay. This will also work when the system was powered off. It
  does imitate anacron but doesn't use it. Instead Back in Time writes it's own
  time-stamp after each successful backup and add a 
`
crontab
`
 job which will
  start Back in Time every 15min (or every hour if configured for weeks). If
  the configured delay is not done yet it will just exit immediately. If an
  error occurred during taking the backup it won't write a new time-stamp and
  so will try again after 15min/one hour.
- 
**
When drive get connected (udev)
**
: this schedule will start a new backup
  as soon as the USB/eSATA/Firewire drive get connected. You can configure a
  delay (hours, days or weeks like in schedule Repeatedly) so it won't start on
  every new connection. This will add a new udev rule in
  
`
/etc/udev/rules.d/99-backintime-<user>.rules
`
 using the partitions UUID. If
  using KDE you need to enable auto-mount for the device in System-Settings.
- 
**
Every Week
**
: start a new backup on a configurable week-day/time every
  week. If the computer is not running at the configured time there will be no
  new backup for the week.
- 
**
Every Month
**
: start a new backup on a configurable day/time every
  month. If the computer is not running at the configured time there will be no
  new backup for the month.
!!! note
    For hourly schedules (every hour, every x hours, and custom hours),
    there will be an option to specify how many minutes after the hour the
    schedule should run. This can be used to prevent multiple backup profiles
    from running at the same time.

## Include

![Settings - Include](_images/light/settings_include.png#only-light)
![Settings - Include](_images/dark/settings_include.png#only-dark)

## Exclude

![Settings - Exclude](_images/light/settings_exclude.png#only-light)
![Settings - Exclude](_images/dark/settings_exclude.png#only-dark)

### Understanding Exclude Patterns

Exclude patterns in Back in Time allow you to specify files and directories that should be skipped during backup. These patterns use the same syntax as rsync exclude patterns, giving you powerful and flexible control over what gets backed up.

#### Pattern Types and Wildcards

- **`*`** - Matches any number of characters within a single directory level
- **`**`** - Matches any number of characters across multiple directory levels (recursive)
- **`?`** - Matches exactly one character
- **`[abc]`** - Matches any one of the characters within the brackets
- **`[a-z]`** - Matches any character in the range

#### Absolute vs Relative Paths

- **Absolute patterns** start with `/` and match from the root of your backup source
- **Relative patterns** don't start with `/` and can match anywhere in the directory tree
- **Directory-only patterns** end with `/` and only match directories

#### Pattern Matching Examples

- `*.tmp` - Excludes all `.tmp` files anywhere in the backup
- `/home/user/Downloads/` - Excludes only the specific Downloads directory
- `Downloads/` - Excludes any directory named Downloads anywhere
- `**/.git/` - Excludes all `.git` directories recursively
- `*.log` - Excludes all `.log` files
- `/var/cache/**` - Excludes everything under `/var/cache/`

### Common Exclude Pattern Examples

#### System and Cache Files
```
**/.cache/
**/.thumbnails/
**/Trash/
**/.DS_Store
**/desktop.ini
```

#### Development Files
```
**/node_modules/
**/.git/
**/*.pyc
**/__pycache__/
**/build/
**/dist/
```

#### Media and Large Files
```
**/*.iso
**/*.dmg
**/*.img
**/VirtualBox VMs/
**/*.vmdk
```

#### Browser Data (if you want to exclude)
```
**/.mozilla/firefox/*/Cache/
**/Google/Chrome/Default/Cache/
**/.config/google-chrome/Default/Cache/
```

### Advanced Tips

- Use the preview feature to test your patterns before running a backup
- Patterns are processed in order - more specific patterns should come before general ones
- Remember that excluding parent directories will exclude all their contents
- Use `rsync --dry-run` to test complex patterns outside of Back in Time

### Reference Documentation

For complete details on exclude pattern syntax, refer to the [official rsync documentation](https://download.samba.org/pub/rsync/rsync.1#FILTER_RULES) on filter rules.

## Remove & Retention
Also known as _Auto-remove_ In previous versions of _Back In Time_.

![Settings - Auto Remove](_images/light/settings_autoremove.png#only-light)
![Settings - Auto Remove](_images/dark/settings_autoremove.png#only-dark)

## Options

![Settings - Options](_images/light/settings_options.png#only-light)
![Settings - Options](_images/dark/settings_options.png#only-dark)

## Expert Options

![Settings - Expert Options](_images/light/settings_expert_options.png#only-light)
![Settings - Expert Options](_images/dark/settings_expert_options.png#only-dark)

## User-callback

For more information on user callback see [this](user-callback.md).
