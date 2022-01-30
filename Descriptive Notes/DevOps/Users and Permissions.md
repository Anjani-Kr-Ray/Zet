# Users and Permissions
### Linux Accounts
There are 3 User Categories. They are:
1. Superuser Account
	* Root User - unrestricted permissions
	* For administrative tasks: Need to login as Root user or execute commands as root (sudo commands)
2. User Account
	* A regular user we create to login
	* E.g. tom -> /home/tom
3. Service Account
	* Relevant for Linux Server Distros
	* Each service will get its own user
	* E.g. mysql user will start mysql application
	* Best practice for security
	* Don't run services with root user!

> __Note:__ 
> * Always 1 Root User per computer
> * can have multiple regular users and service users

### Why multiple standard users?
* to share computer
* many companies use Windows for their employees
* usually employees can login to your account on every computer

### How does this work?
1. For Windows
	* Windows is able to centrally manage users
	*  Admins add users to the system
	* All computer are connected to this system
	* when someone tries to login, OS checks with the system
	* Only access to your home folder
2. For Linux
	* Linux doesn't has this centrally managed system
	* user accounts are manages on that specific hardware

### Multiple Users on a Server
* For Linux having Multi-user is important for servers
* usually teams administer a server
* Why having a user for each team member is important?
	* They need a non root user
	* Permissions per team member i.e., give more privilege to senior than junior admins
	* traceability - to know who did what on the system so that if any problem arise then someone could help

### How to manage Permissions?
1. User Level:
	* Give permission to user directly

2. Group Level:
	* Group users into Linux Groups
	* Give permission to that group
	* This is best way to manage multi users

### User Management in Practice
* User account info is stored in /etc/passwd folder.
* Format: **user_name: password: uid: gid: gecos: homedir: shell**
* password is sensitive so it is stored in another file: `/etc/shadow`
* uid (user ID): every user has a unique id and root user has `UID 0` reserved
* gid (Group ID): the primary group id is stored in `/etc/group` file
* gecos (User ID info): commet field for extra information about users
* homedir: home directory of user
* shell: absolute path of default shell
* __sudo adduser <user_name> :__ add a new user
* whenever we add a new user by default a group is created with user name and with next available gid
* __sudo passwd <user_name>:__ change password.
* __su - <user_name>:__ login as username
* __su - :__ login as root user
* __sudo groupadd <group_name>:__ create new group
* By default, system assigns the next available GID from the range of group IDs specified in the login.defs file
* __Different user and Group commands__

| adduser, addgroup, deluser, delgroup | useradd, groupadd, userdel, groupdel |
| :---: | :---: |
| interactive and more user friendly | Less interactive |
| default values will be provided by the system automatically | we need to provide the infos ourself |
| use when executing manually | when executing in an automated way |

* __sudo usermod -g <group_name> <user_name> :__ change primary group of user to given group name
* __sudo usermod -G <group_name1> <group_name2> <user_name> :__ override secondry group of user to given group names
* __sudo usermod -aG <group_name1> <group_name2> <user_name> :__ append new given groups to existing secondry group of user 
* __groups <user_name>:__ to display groups of user
*  __sudo useradd [options] <user_name>:__ create a new user with different options
	* add -G <group_name> to add user to the specified group
	* -d custom home directory
	* and other options for shell etc.
* __sudo gpasswd -d <user_name> <group_name>:__ remove user from the specified group

### File Ownership and Permission
* User Permissions are related to reading, writing and executing files
* __ls -l :__ print files in a long listing format
* __Ownership:__
	* who owns the file/directory?
	* There are 2 ownership levels of a file/directory: 
		1. which user owns the file? --> Owner is the user, who created the f
		2. which group owns the file? --> Owning group is the primary group of that user
	* __sudo chown <user_name>:<group_name> <file_name>__ : change ownership
	* __sudo chown <user_name> <file_name>__ : change user
	* __sudo chgrp <group_name> <file_name>__ : change group
* __Linux Permissions:__
	* __d <span style="color:tomato">r w x</span> <span style="color:cyan">r w x</span> <span style="color:violet">r - x</span>__
	* First character represents the File Type: 
		* `-` regular file
		* `d` directory
		* `c` character device file
		* `l` symbolic link etc.
	* Next 3 characters represents permission for owner, another 3 character represents permission for group and last 3 characters represents permission for other.
		* `r` Read
		* `w` Write
		* `x` Execute
		* `-` No permission
	* __sudo chmod @\* <file_name>:__ removes/add permission from the file for all the owners. 
		* Replace @ with + or - to add or remove permission respectively
		* Replace \* with r, w, x for removing read, write or execute permission respectively
	* __sudo chmod \#@\* <file_name>:__ removes/add permission from the file for specific owner. 
		* Replace @ with + or - to add or remove permission respectively
		* Replace \# with u, g, o to remove permission for user, group or others respectively
		* Replace \* with r, w, x for removing read, write or execute permission respectively 
	* There is second way to change permission. For example, we want to change permission of file for group. Then we can use command: `sudo chmod g=rw- <file_name>`. This will give group read and write permission only. According to our requirement we can have any combination of r, w, x, -
	* The third way is to use so called **Absolute(Numeric) Mode**

	    | Number | Permission | Symbol |
		| :---: | :---: | :---: |
		| 0 | No Permission | --- |
		| 1 | Execute | --x |
		| 2 | Write | -w- |
		| 3 | Execute + Write | -wx |
		| 4 | Read | r-- |
		| 5 | Read + Execute | r-x |
		| 6 | Read + Write | rw- |
		| 7 | Read + Write + Execute | rwx |

		* For example `sudo chmod 777 <filename>` to give user, group and others read, write and execute permission 

