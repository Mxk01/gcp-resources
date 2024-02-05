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
## Update and install packages on a VM:
```bash sudo apt-get update
sudo apt install -y nginx
```
## Check if Nginx is running:
```bash
ps auwx | grep nginx
```

## Access the external IP of the VM in a web browser.
Use the Cloud Console to create a new instance or run the following CLI command:
```bash
gcloud compute instances create [INSTANCE_NAME] --machine-type e2-medium --zone=$ZONE
```

```bash
gcloud compute instances create gcelab2 --machine-type e2-medium --zone=$ZONE
```

## Connect to a VM using SSH:
```bash
gcloud compute ssh [INSTANCE_NAME] --zone=$ZONE
```
Use EXPORT to create global variables for flags, e.g., --zone=$ZONE.

