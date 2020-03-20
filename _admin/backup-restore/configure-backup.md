---
title: [Configure periodic backups]

last_updated: 3/4/2020
toc: true
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---
You can configure ThoughtSpot to backup automatically at specified times. The policy allows you to control the type, frequency, retention periods (first-in-first-out), and output location for a periodic backup.

A periodic backup uses the same steps as creating a backup manually. However, you do not have to specify a snapshot name, the system uses the most recent backup. You can backup to a local file system or [mount a NAS (network attached storage) file system]({{ site.baseurl }}/admin/setup/NAS-mount.html#) to hold the backup. A NAS is recommended. Make sure you have adequate space to store the number of backups you want to archive.

## Default policy format

The format for a policy includes the following:

```
name: "name_for_backup"
param {
    mode: FULL | DATALESS | LIGHTWEIGHT
    type: STANDALONE
}
schedule {
    period {
      number: integer
      unit: MINUTE | HOUR | DAY
    }
    retention_policy {
          time {
          number: integer  
          unit:  MINUTE | HOUR | DAY
        }
        capacity: integer
      }
  }
  offset_minutes_from_sunday_midnight: integer
}
directory: "NAME"
storage_type: NAS | LOCAL  
```

## Before you begin
Before creating a policy, make sure you have read [Understand backup/snapshot
schedules](how-to-create-a-schedule.html) for information on configuring a
`schedule` element. In addition, you must specify:

|Element|Description|
|-------|-----------|
|`mode`|The backup mode. `FULL` backups are necessary for restoring a cluster. See [Work with backups](backup-modes.html) for details on each backup mode.|
|`type`|Currently, only `STANDALONE` is supported.|
|`directory`|The location on the disk to place the backup.|
|`storage_type`|The type of storage you are using. `NAS` storage is recommended for `FULL` backups.|

## Create a backup policy

Backups cannot start when another backup is still running. So, choose a
reasonable frequency for the mode in you policy. For example, a `FULL` backup
takes longer than a `DATALESS` backup. Consider the load on the system when
configuring. Do not backup up when the system would experience a heavy load. For
example, you may want to take `FULL` backups late in the evening or on weekends.

The retention system deletes the oldest stored backup and the corresponding
snapshot on a first-in-first-out basis (FIFO). This means that if you set a
bucket retention of 1 the system stores a single backup at any one time. The
system  deletes the older backup after the new full backup is successful.

### Configure using tscli

To configure periodic backups using the tscli:

1. Log in to the Linux shell using SSH.
2. Find a directory with enough disk space to support the `retention_policy number` you configure.

   You can use `df -h` to see free disk space and `tscli snapshot ls` to view existing snapshots and their size on disk.

3. Use the `tscli backup-policy create` command.

   The command opens a `vi` editor for you to configure the backup policy.

4. Write and save the file to store your configuration.

   By default, newly created policies are automatically enabled. To disable a policy, use the `tscli backup-policy disable` command.

5. Verify the policy using the `tscli backup periodic-config <name>` command.

### Doing more with backup

The following table lists some additional backup commands you can use.

|To|Command|
|--|--------|
|List present backup policies.|`tscli backup-policy ls`|
|Show a backup policy.|`tscli backup-policy show <name>`|
|Check the status of a policy.|`tscli backup-policy status <name>`|
|Change an existing policy.|`tscli backup-policy update <name>`|
|Disable or enable an existing policy.|`tscli backup-policy disable` or `enable`|
|Delete a policy|`tscli backup-policy delete <name>`|

Finally, you can time a `crontab` job with your periodic backup configuration to
move a backup to longer term storage. Simply create a `crontab` job that moves
the backup to a location outside of the `directory` defined in the periodic
schedule.
