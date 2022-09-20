# project-7-DEVOPS-TOOLING-WEBSITE-SOLUTION
In this project, we would learn how to build a DevOps tooling website.

## Table of Contents
- [Introduction](#introduction)
- [Step1](#Step 1 - Prepare NFS Server)
- [Step2](#Step 1 - Prepare NFS Server)



### Introduction






### Step 1 - Prepare NFS Server
In this step, we would prepare the Network File system server.
1. Create a new EC2 instance with RHEL Linux 8 AMI.

    Results:
    ![image](img/ec2.png)


2. Configure LVM on the server.
- Create and attach 3 volumes to the server.

    Results:
    ![image](img/volumes.png)

- Connect to your Linux instance and check if the volumes are attached using the following command:
    ```
    lsblk
    ```
    Results:
    ![image](img/lsblk.png)

- Use gdisk utility to create a single partition on each of the 3 disks.
    ```
    sudo gdisk /dev/nvme1n1 /dev/nvme2n1 /dev/nvme3n1
    ```
    Results:
    ![image](img/gdisk.png)

- Then install the lvm2 package using the following command:
    ```
    sudo yum install lvm2
    ```
    and then run the following command to check for available partitions:
    ```
    sudo lvmdiskscan
    ```
    Results:
    ![image](img/yum.png)
    ![image](img/lvmdiskscan.png)