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
- Type n to create a new remote.
- When prompted, give the remote a name, e.g., manage_backup.
- Choose drive as the storage type.
- For client ID and secret, leave them empty unless you have a custom Google API project.
- For the root folder ID and service account file, leave them empty.
- Say n to advanced config unless you need specific settings.
- Choose n if you are running on a machine without a web browser. If you're on a machine with a web browser, you can choose y.
- Complete the authentication in your web browser by logging into your Google account and authorizing rclone.
- Once authenticated, rclone will save the configuration




