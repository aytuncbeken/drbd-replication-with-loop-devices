# DRDB Disk Replication with Loop Devices
This repository consist of ansible roles for creating block device level replication using [DRBD](https://docs.linbit.com/).
## Details
Ansible role is developed to acquire below steps
- Create disk image file
- Create loop device from image file
- Create DRBD cluster and get up
- Set first host as Primary and rest as Secondary
- Mount DRBD device as directory
## Usage
First add you hosts to ```hosts``` file under group ```servers```. The first host in this list will be set as **Primary** in the cluster.
<br>
Change parameter values in ```vars.yml``` for your needs. Parameters are explained below.
- disk_size: size of the image file which will be created. Also this value be the size of the clustered disk
- mount_point: full path of the directory name where DRBD clustered disk will be mounted


Start ansible playbook by running command below
```
ansible-playbook -i hosts install.yml
```
After success full install, you can access to directory, path given in the parameter **mount_point**, in the first host.
