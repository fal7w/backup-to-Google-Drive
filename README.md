# Backup with `rclone` to Google Drive
This guide explains how to use rclone to copy files from a local directory to Google Drive. The example below demonstrates copying a directory containing backup files to a specified folder on Google Drive.


### Prerequisites: 
- A system running a Unix-based OS (e.g., Ubuntu, Debian) or Windows.
- Access to a Google Drive account.


### Step 1: Installing rclone
#### 1.1 Install on Linux
To install rclone on a Linux system, run the following command:
``` bash
curl https://rclone.org/install.sh | sudo bash
```
This command downloads the installation script and runs it with root privileges to install rclone on your system.

### Step 2: Configuring rclone with Google Drive
Once rclone is installed, you'll need to configure it to work with Google Drive.

#### 2.1 Start the Configuration
Run the following command to start the configuration process:
``` bash
rclone config
```

#### 2.2 Create a New Remote
- Type `n` to create a new remote.
- When prompted, give the remote a name, e.g., `manage_backup.`
- Choose `drive` as the storage type.
- For client ID and secret, leave them empty unless you have a custom Google API project.
- For the root folder ID and service account file, leave them empty.
- Say `n` to advanced config unless you need specific settings.
- Choose `n` if you are running on a machine without a web browser. If you're on a machine with a web browser, you can choose `y`.
- Complete the authentication in your web browser by logging into your Google account and authorizing `rclone`.
- Once authenticated, `rclone` will save the configuration


#### 2.3 Verifying the Configuration
After setting up the remote, verify it by listing the contents of your Google Drive:

``` bash
rclone lsd manage_backup:
```
This command should list the directories in the root of your Google Drive.

### Step 3: Copying Files to Google Drive

#### 3.1 Copy Files to Google Drive Using `rclone`
Use the `rclone copy` command to copy the files from your local directory to the Google Drive remote.

``` bash
rclone copy /path/to/local/directory mydrive:/path/in/drive/
```

#### Example:
``` bash
rclone copy /root/borg-extract/root/lago_backup manage_backup:manage_systems
```

#### 3.2 Verify the Files on Google Drive
After the copy operation completes, you can verify that the files were successfully copied by listing the contents of the destination directory on Google Drive.
``` bash
rclone ls manage_backup:manage_systems
```
This command will display a list of files in the manage_systems directory on your Google Drive.



### Conclusion
By following these steps, you can easily back up your files to Google Drive using rclone. This method provides a flexible and powerful way to manage your backups, especially when combined with automation through cron jobs.






