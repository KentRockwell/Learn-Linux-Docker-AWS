# Lesson 2
This lesson is focused on the Linux file system.


Log into your Cloud9 and open terminal.

## Display Usage in Megabytes and Gigabytes

```bash
df -h
```

## Understanding the Output Format
Your output may have more entries. The columns should be self-explanatory:

* Filesystem – This is the name of each particular drive. This includes physical hard drives, logical (partitioned) drives, and virtual or temporary drives.
* Size – The size of the filesystem.
* Used – Amount of space used on each filesystem.
* Avail – The amount of unused (free) space on the filesystem.
* Use% – Shows the percent of the disk used.
* Mounted on – This is the directory where the file system is located. This is also sometimes called a mount point.


The list of filesystems includes your physical hard drive, as well as virtual hard drives:

* **/dev/sda2** – This is your physical hard drive. It may be listed as /sda1, /sda0, or you may even have more than one. /dev stands for device.
* **udev** – This is a virtual directory for the /dev directory. This is part of the Linux operating system.
* **tmpfs** – You may have several of these. These are used by /run and other Linux processes as temporary filesystems for running the operating system. For example, the tmpfs /run/lock is used to create lockfiles. These are the files that prevent multiple users from changing the same file at the same time.


## Display a Specific File System
The df command can be used to display a specific file system:

```bash
df -h /dev/sda2
```

You can also use a backslash:

```bash
df -h /
```

This displays the usage on your primary hard drive. Use the mount point (in the Mounted on column) to specify the drive you want to check.


## Display File Systems by Type
To list all file systems by type, use the command:

```bash
df -ht ext4
```

This lists drives with the ext4 type, in human-readable format.


## Check Disk Space in Linux With du Command
The du command displays disk usage. This tool can display disk usage for individual directories in Linux, giving you a finer-grained view of your disk usage. Use it to display the amount of space used by your current directory:

```bash
du
```


This shows how much space the current directory uses.

example of how much space is left in a linux directory
To specify the directory or file, check use the following options:

```bash
du -hs /etc/kernel-img.conf
```

```bash
du -hs /etc
```

With the second command, you may have noticed a permission denied error message. This means the current user doesn’t have the privileges to access certain directories. Use the sudo command to elevate your privileges:

```bash
sudo du -hs /etc
```


# AWS EC2

## Cloud9 Disk Usage Data
From the previous steps you should know:

1. Where your disk space is beign consumed
2. Cleaned up files and directories no longer needed
3. Know how much total disk space you need
4. Know how to divide up additiaon disk space added


## Cloud9 Storage Increase
1. Log into AWS
2. Select Manage EC2 Instance
3. Select Storage
4. Select Storage ID
5. Select Action
6. Select New Disk Size
7. Select Okay

Check the console for when AWS has completed adding new storage.


## Cloud9 EC2 Linux 2023 Operating System
[Extend a Linux file system after resizing a volume]( https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html)


[Extend a Linux file system after resizing a volume]( https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html)

Now the operating system needs to address the newly added storage (virtual hardware) you jut added in the AWS console.


Use the following procedure to extend the file system for a resized volume.


Note that device and partition naming differs for Xen instances and Nitro instances. To determine whether your instance is Xen-based or Nitro-based, use the describe-instance-types AWS CLI command as follows:

```bash
aws ec2 describe-instance-types --instance-type instance_type --query "InstanceTypes[].Hypervisor"
```


Check whether the volume has a partition. Use the lsblk command.

```bash
sudo lsblk
```





Extend the partition. Use the growpart command and specify the partition to extend.


**Important**


*	Note the space between the device name (nvme0n1) and the partition number (1).*

```bash
sudo growpart /dev/nvme0n1 1
```
