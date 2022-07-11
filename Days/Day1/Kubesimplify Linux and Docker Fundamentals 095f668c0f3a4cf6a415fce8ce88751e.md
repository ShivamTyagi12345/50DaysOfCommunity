# Kubesimplify Linux and Docker Fundamentals

Created: July 11, 2022 7:48 PM
Reviewed: No

*Linux is Nothing more than a group of files*

### Head over to [Killercoda](https://killercoda.com/playgrounds/scenario/ubuntu) for a simulated terminal

`Command To start anew` : **clear**

`Command To list all the files` : **ls /** 

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled.png)

`Command To see the present working directory` : **pwd**

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%201.png)

**Note**: ***root*** is a quite important to look out for and should be handled with caution for secured control over your files.

Various popular distributions/Distros  that are available are Ubuntu ,Arch , Fedora etc. Read the function of various contents of the present working directory  that are available after running

 `**ls /**`

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%202.png)

## Scenario 1😍

Useful command to find out information on a ubuntu distribution `lsb_release -a`

here `-a` is a flag to display “all” of the information

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%203.png)

**Note**: if we want to know more about the various flags  use: `man lsb_release`  Press **q** to get back to your terminal

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%204.png)

Another way to get information outta our OS  is to use 

1. `/man cat`
    
    ![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%205.png)
    
2. `lsmem` Get info about memory
3. `cat /etc/os-release` This is an important command to just get  info that may or maynot be provide using `man lsb_release`

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%206.png)

## Scenario 2 🐱‍🏍SYS-LOG: important for trouble shooting via system logs

- `find`: this will list a clear instruction to find the required logs
- `find / -name 'syslog'` this helps with a clear and precise info about the desired file name ,here, *syslog*

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%207.png)

- `cat syslog | grep ubuntu` This is one of the piping commands and this is specially helpful to search out files by their specific names and then debug the error at our own pace. This is thus a useful command to search through long files such as **syslog**.

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%208.png)

## 🎇Scenario 3: Creating a user

- `useradd -D`: this creates a user, and we can easily see the Defaults that are going to be placed on the user when we create that user
    
    ![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%209.png)
    
- `echo $SHELL`  SHELL basically allows us to work with certain commands that can be exclusive to the distribution  we are using
    
    ![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2010.png)
    
- `useradd -D -s /bin/bash`   this add the new user using the output of `echo $SHELL`
- 

**NOTE:**  reach to a previously ran command use **`ctrl+E`**

Running `useradd -D`  now changes the default shell address of the  user

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2011.png)

Finally  create new user and password using `useradd -m *abcd*` and `passwd abcd`

 

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2012.png)

Now switch over to the new user using  `su - abcd`

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2013.png)

Next we have to add the user to a group

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2014.png)

**Review : These commands are ran so far . 🎀**

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2015.png)

🥇Yay these are all the things we have accomplished so far

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2016.png)

## Final Touch: Package managers

[Cheatsheet](https://github.com/chadmcrowell/linux-docker)🎉

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2017.png)

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2018.png)

- changing the prompt
    
    ![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2019.png)
    
- How does a package manager know where to install the right updates.  This is where you can get more info from.

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2020.png)

🎈INSTALLING Docker

1. `sudo apt install -y ca-cerficates`

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2021.png)

1. `sudo apt install curl`  curl is a important command to monitor where the traffic is going and if we are getting responses from the traffic

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2022.png)

1. `sudo apt install gnupg`: checks the software is coming from a trusted sources

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2023.png)

1. `sudo apt install -y lsb-release`

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2024.png)

```markup
# GPG, or GNU Privacy Guard, is a public key cryptography implementation. This allows for the secure transmission of information between parties and can be used to verify that the origin of a message is genuine
# apt-key is a program that is used to manage a keyring of gpg keys for secure apt.
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# When installing packages using apt the packages are downloaded from one or more apt software repositories.
# An APT repository is a network server or a local directory containing deb packages and metadata files that are readable by the APT tools.
# While there are thousands of application available in the default Ubuntu repositories, sometimes you may need to install software from a 3rd party repository.

# add docker 3rd party repository
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# pull down packages locally
apt search docker-ce
sudo apt update
apt search docker-ce

# install  Docker Engine, containerd, and Docker Compose
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin

# show docker-ce package metadata from repository
# madison is the name of the Debian archive management tool used for all debian and debian-like distros
# apt-cache madison docker-ce

# install a specific version
# sudo apt install -y docker-ce=5:20.10.17~3-0~ubuntu-focal docker-ce-cli=5:20.10.17~3-0~ubuntu-focal containerd.io docker-compose-plugin

# verify its all working
docker run hello-world

```

## Next Up 🎊  [Permissions in a Linux File Sy

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2025.png)

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2026.png)

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2027.png)

```markdown
# pipe to less
# cat /var/log/syslog | less
# cat /var/log/syslog | grep file
cat /var/log/syslog | grep ubuntu | less

# pipe to a file
# history | grep ls > commands.txt
# history | grep history >> commands.txt

# create script
vim script.sh
# type bash

# change ownership of file
# chown chad:root file1.txt

# change just the user
# chown chad file1.txt

# change just the group
# chgrp root file1.txt

# take away write permissions for the group
# chmod g-w file1.txt

# give executable permission to the group
# chmod g+x file1.txt

# give owner permission to execute
ls -al # verify chris is owner
chmod u+x script.sh
ls -al # verify change

# give other permissions to execute
# chmod o+x script.sh
# give executable for all
# chmod +x script.sh

vim script.sh
# copy and paste from this 

./script.sh
```

# Docker🎇🎉

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2028.png)

![Untitled](Kubesimplify%20Linux%20and%20Docker%20Fundamentals%20095f668c0f3a4cf6a415fce8ce88751e/Untitled%2029.png)

```markdown
# types of cgroups on the system
ls /sys/fs/cgroup/

# look at memory cgroup
ls /sys/fs/cgroup/memory/

# all processes will use this cgroup by default
# to use a different cgroup beside the default, you must create a new and assign the process to it

# create a new cgroup and assign a process to it
cd /sys/fs/cgroup
mkdir memory/chad
ls memory/chad/

# the maximum a cgroup is allowed is 'memory.limit_in_bytes'

# use lscgroup utility to see cgroups from the host side

# compare memory cgroups before and after starting a new container with runc
# first, take a snapshot of before we make a change
cd
apt install -y cgroup-tools
lscgroup memory:/ > before.memory

# start a new container
docker container run --detach --name nginx nginx

# take an after snapshot
lscgroup memory:/ > after.memory

# compare
diff before.memory after.memory

# this is relative to the root of the memory cgroup
# inspect cgroup from the host
cd /sys/fs/cgroup/memory/
ls system.slice/docker-3076b152051a7543f4724f8950a55f84828387e30170f08e3804c03936566799.scope/

# from inside the container, the list of its own cgroups is aviailble from the /proc directory
docker exec -it nginx bash
# from inside run 'cat /proc/$$/cgroup'

# notice (on last line) that the memory cgroup is exactly what you found on the host
# once we have the cgroup name, we can modify the parameters

# see how the mem limit is 
cat system.slice/docker-3076b152051a7543f4724f8950a55f84828387e30170f08e3804c03936566799.scope/memory.limit_in_bytes

# by default, no limit, so this number represents all memory available to host machine (overall)

# this is a problem because a single container can use up all memory if it wants (if memory leak)

# limit the memory for a container
docker rm -f nginx
docker container run --detach -m 6MB --name nginx nginx
docker exec -it nginx bash
# from inside run 'cat /proc/$$/cgroup'
# exit

# cd
# lscgroup memory:/ > after.memory
# diff before.memory after.memory
# cd /sys/fs/cgroup/memory/

cat system.slice/docker-653e68c52719eff5aa7f6e29f7b17aa2a0a7a2cd6ab6375148e5502021fe121f.scope/memory.limit_in_bytes

# see the change in memory limit

# assign a process to a cgroup by write the process ID to the cgroups.procs file for that cgroup

# get the PID for the container
docker container top # 46981

# change memory limit for cgroup
cd chad
echo 6291456 > memory.limit_in_bytes
cat memory.limit_in_bytes

# assign PID to cgroup
echo 46981 > cgroup.procs

# cat out what memory cgroup is assinged to that process
cat /proc/46981/cgroup | grep memory

######################################################

# NAMESPACES

#######################################################

# by putting a process in a namespace, you can restrict the resources that are visible to that process

# a process has exactly one namespace of each type
# see the namespaces 
lsns

# for non-root users, ns list may be incomplete
sudo lsns

# use namespaces to create something that behaves like a container
# start with the UTS namespace (handles hostname and domain names)
# put a process in it's own UTS namespace, to change it's hostname (different than host)
hostname

# run a container to get a random ID for the hostname (not the name of the container)
docker container run --rm -it --name hello ubuntu bash
# inside container run 'hostname'
# inside container run 'exit'

# you can change the hostname of the container
# using the unshare command, you can create a process that has a UTS namespace of its own
sudo unshare --uts sh
hostname
hostname experiment
hostname
exit

# this ran a sh shell in a new process that has a new UTS namespace (not effect host)
hostname

# isolate process IDs
# run ps inside a container to get list of processes only running inside the container
docker container run --rm -it --name hello ubuntu bash
# inside container run 'ps -eaf'

# this is because of the process ID namespace
# PID namespace restricts the PIDs you can see

# use unshare to create new pid namespace
sudo unshare --pid sh
# run 'whoami'
# run 'whoami'
# run 'whoami'
# run 'ls'

# this did not work because it created a new PID with every command (following the process heirarchy)

# view process heirarchy by opening a new tab (second terminal) while the unshare cmd is running in the first
ps fa

# the sh process is a child of the sudo process
# get around this by using the --fork
sudo unshare --pid --fork sh
# run 'whoami'
# run 'whoami'

# no problem running the command multiple times

# view process heirarchy (in second terminal)
ps fa

# the fork version is a chile of unshare

# from the first terminal, run ps
ps
ps -eaf

# still showing processes on the entire host because it reads virtual files in /proc

# look at the /proc dir to see why
ls /proc

# every number refererences a different PID
# /proc/<pid>/exe is a symbolic link to the executable
ps
ls /proc/32440
ls -l /proc/32440/exe

# /proc is under root, so it's giving us PID under root (all of them instead of just for our namespace)
# this means that there needs to be a separate copy of /proc to return information only inside new namespace (because /proc is under root)

# change the root directory with chroot
# docker does this automatically 
# this moves the root directory for a process to point to a different location within the filesystem (not /proc)
# first, you must grab a filesystem to run /bin/bash and other command executables
cd
mkdir alpine
cd alpine
curl -o alpine.tar.gz http://dl-cdn.alpinelinux.org/alpine/v3.16/releases/x86_64/alpine-minirootfs-3.16.0-x86_64.tar.gz
tar -xvf alpine.tar.gz
rm alpine.tar.gz
cd ..

# you now have a copy of the alpine filesystem
# use chroot to move into the alpine directory
sudo chroot alpine ls

# only the child process 'ls' got it's own root directory 

# try again with running a shell as a child process
sudo chroot alpine sh
ls
ls /home
exit

# this changes the root for a process just like a container

# run chroot in a new namespace
sudo unshare --pid --fork chroot alpine sh

# ps will now show the processes just inside the PID namespace
# first mount proc as pseudofilesystem of type proc, independent from proc on host
mount -t proc proc proc
ps
exit

# Mount Namespaces
```