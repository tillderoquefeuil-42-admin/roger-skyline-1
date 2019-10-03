# roger-skyline-1
Let you install a Virtual Machine, discover the basics about system and network administration as well as a lots of services used on a server machine.

## table of contents
* [Legend](#legend)
* [Variables](#variables)
* [Environnement](#environnement)
* [VB settings](#vbsettings)
* [VM installation](#vminstallation)
* [User set up](#user)
* [Update/grade](#upgrade)
* [Static IP](#staticip)
* [SSH](#ssh)
* [Firewall](#firewall)
* [Scans protection](#scans)
* [Stop services](#stopservices)
* [Cron update](#cronupdate)
* [Cron monitoring](#cronmonitoring)


## Legend <a id="legend"></a>
_*#OH#*_ : run on the host machine

_*#IN#*_ : if needed

```
$ command to run
```

```
> return
```

```diff
!file to edit
```


## Variables <a id="variables"></a>
Name | Value
---- | ----
HOSTNAME | debian
ROOT_PSWD | root
USERNAME | till
USER_PSWD | till
USER_MAIL | tde-roqu@student.42.fr
IP | 10.12.130.30
NETMASK | 255.255.255.252 / 30
GATEWAY | 10.12.254.254
SSH_PORT | 55555
HTTP_DEFAULT_PORT | 80
HTTPS_DEFAULT_PORT | 443
GIT_REPO | https://github.com/tillderoquefeuil/doggos.git
REPO_NAME | doggos.com
PASS_SSL | tillssl


## Environnement <a id="environnement"></a>
[VirtualBox](https://www.virtualbox.org/)
[Debian Img](https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/)


## VB settings <a id="vbsettings"></a>
New VM > settings > Storage > Controller: IDE empty disk : Choose Virtual Optical Disk File

- [x] Live CD/DVD

New VM > settings > Network > Adapter 1 > Attached to: Bridged Adapter


## VM installation <a id="vminstallation"></a>
```
> Install

Language
> English

Location for timezone
> Other > Europe > France

Local settings
> United Kingdom

Keyboard
> British English

Hostname
> <HOSTNAME>

Domain name
> *blank*

Root password
> <ROOT_PSWD>

Fullname for new user
> <USERNAME>

Username
> <USERNAME>

New user password
> <USER_PSWD>

Partitioning method
> Guided - use entire disk

Select disk to partition
> SCSI2

Partitioning scheme
> Separate /home, /var, and /tmp partitions

Overview
> Finish partitioning and write changes to disk

Write the changes to disks
> Yes

Scan another CD or DVD?
> No

Debian archive mirror country
> France

Debian archive mirror
> deb.debian.org

HTTP proxy
> *blank*

Participate in the package usage survey
> No

Software to install
> ssh-server
> standard utilities system

Install the GRUB boot loader
> Yes

Device for boot loader installation
> /dev/sda
```

VM > settings > Storage > Controller: IDE Secondary Master: Remove Disk From Virtual Drive
- [ ] Live CD/DVD

```
Installation is complete
> Continue
```

```
> debian login: <USERNAME>
> Password: ****
```


## User set up <a id="user"></a>
```
$ su
$ apt-get install sudo
$ sudo usermod -a -G sudo <USERNAME>
$ nano /etc/sudoers
```

```diff
!root ALL=(ALL:ALL) ALL
!<USERNAME> ALL=(ALL:ALL) ALL
```

```
$ su - <USERNAME>
```

***TEST***
```diff
$ sudo -v
-> [sudo] password for <USERNAME>:
+> Sorry, user <USERNAME> may not run sudo on <HOSTNAME>.
```


## Update/grade <a id="upgrade"></a>


## Static IP <a id="staticip"></a>


## SSH <a id="ssh"></a>


## Firewall <a id="firewall"></a>


## Scans protection <a id="scans"></a>


## Stop services <a id="stopservices"></a>


## Cron update <a id="cronupdate"></a>


## Cron monitoring <a id="cronmonitoring"></a>
