# Google Cloud Platform Quick Start Guide

This README provides a quick start guide for setting up and managing resources on Google Cloud Platform (GCP) using the command line interface (CLI) and Cloud Console.

## Initialization

```bash
gcloud init
```

Access Cloud Shell to use the CLI within your web browser or connect to a virtual machine (VM) using the CLI.

## Project Configuration
A Google Cloud project organizes resources and services.
Obtain the Project ID, a unique identifier for your project.
Use gcloud config list project to view the current project.

## Enabling APIs

Go to the API Library in Cloud Console.
Search for the desired API and enable it.

## Authentication and User Information

```bash gcloud auth list
gcloud config list project
```
Use these commands to view the current username, email, and project ID.

## Setting Region and Zone

```bash
gcloud config set compute/region [REGION]
```
## Export region and zone as variables:
```bash
export REGION=[REGION]
export ZONE=[ZONE]
```
## Working with Virtual Machines ( Compute Engine)
![GCP VM Instance](https://cdn.discordapp.com/attachments/1081183405779197973/1204074589445947463/image.png?ex=65d368d8&is=65c0f3d8&hm=9b0f1eaeffa747ca0beb10df860676d0b8ac8b21dee9af1106955)
## Update and install packages on a VM:
```bash sudo apt-get update
sudo apt install -y nginx
```
## Check if Nginx is running:
```bash
ps auwx | grep nginx
```

## Access the external IP of the VM in a web browser.
![GCP External IP VM](https://cdn.discordapp.com/attachments/1081183405779197973/1204074589869703250/image.png)
Use the Cloud Console to create a new instance or run the following CLI command:
```bash
gcloud compute instances create [INSTANCE_NAME] --machine-type e2-medium --zone=$ZONE
```

```bash
gcloud compute instances create gcelab2 --machine-type e2-medium --zone=$ZONE
```

## Connect to a VM using SSH:
![GCP SSH VM](https://cdn.discordapp.com/attachments/1081183405779197973/1204074591270604810/image.png)
```bash
gcloud compute ssh [INSTANCE_NAME] --zone=$ZONE
```
Use EXPORT to create global variables for flags, e.g., --zone=$ZONE.

## Connect to a VM using RDP:
The following script will check if the server is ready to accept RDP connection.Some OS components might take a while to load :
```bash
gcloud compute instances get-serial-port-output instance-1
```
Keep repeating this command and press N key. 

## Connecting to a Windows VM with RDP
![GCP VM RDP1](https://cdn.discordapp.com/attachments/1081183405779197973/1204416668105969724/image.png)
Select the Windows Server operating system from BootDisk.

![GCP VM RDP](https://cdn.discordapp.com/attachments/1081183405779197973/1204416522181808149/image.png)
Before connecting to the VM we need to reset the password.We can do it via the CLI or the UI.
```bash
gcloud compute reset-windows-password [instance] --zone [zone] --user [username]
```

### Open RDP on Windows and type in the external IP address of your VM  
For example : 35.237.200.242
Connect to the RDP with username and password provided by the Cloud Engine 
