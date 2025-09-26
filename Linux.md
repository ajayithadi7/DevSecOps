
# 🐧 Linux Fundamentals – My DevOps Journey I’ve started my DevOps journey by learning **Linux fundamentals**. Here’s my full note from today, covering all the topics I practiced. --- ## 📌 What is an Operating System? An **Operating System (OS)** is software that acts as an interface between computer hardware and the user. Every computer must have at least one OS to run other programs. Applications like browsers, MS Office, Notepad, and games need an environment provided by the OS to run. The OS helps you communicate with the computer without knowing its language. --- ## 📌 Linux Overview - **Linux** is a free and open-source operating system known for high security and multi-user capability. - It powers servers, supercomputers, smartphones, desktops, and even home appliances like washing machines, routers, and cars. --- ## 📌 Linux Components ### 🖥 Kernel - Manages hardware components like CPU, memory, and peripheral devices. - It’s the lowest level of the OS and the heart of Linux. ### ⚙️ Daemons - Background services (printing, sound, scheduling, etc.) that start during boot or after login. ### 📝 Shell - An environment where we run commands, programs, and shell scripts. - Accepts input, executes programs, and displays output. - Two types: - **Command-line (CLI):** text commands in a terminal. - **Graphical (GUI):** windows, icons, and buttons. ### 💻 Terminal - A text-based interface to interact with the OS. - Also called CLI, console, or shell. - Available in Linux, macOS, and Windows (Command Prompt / PowerShell). ### 🖊 Command - A specific instruction given to the OS or shell to perform an action or task. --- ## 📌 Linux Distributions Many groups modify Linux OS to meet their needs and release it under different names called **distributions**: RedHat | Ubuntu | Debian | CentOS | Fedora | OpenSUSE | Kali Linux | Amazon Linux | Rocky Linux --- ## 📌 Linux History - **1991:** Linus Torvalds, a student at the University of Helsinki, Finland, began writing a free Unix-like kernel. - Initially named **“Freax”**, later renamed **Linux**. - **1992:** Released under the GNU General Public License (GPL). - Written in **C language**. - Today Linux runs on servers, supercomputers, smartphones, desktops, and even IoT devices. --- ## 📌 Open Source Principles Linux is distributed under an **open-source license**, which means: - Anyone can view, use, modify, and distribute the code. - **Freedom to run** the program for any purpose. - **Freedom to study** how the program works and change it. - **Freedom to redistribute** copies to help others. - **Freedom to share modified versions**. --- ## 📌 Linux Architecture - **Kernel:** Core that manages hardware and software communication. - **Shell:** Allows users to interact with the OS (CLI or GUI). - **Utilities & Commands:** Tools for end-users. --- ## 📌 Practical Session – Linux Commands By default, we’re in the `ec2-user`. For administrative actions, switch to the root user: ```bash sudo -i # switch to root exit # logout back to ec2-user 
suo = “super user do”
🔹 System Commands
uname # OS type uname -r # Kernel version uname -a # Full OS info clear # clear screen (or Ctrl+L) uptime # system running time uptime -p # pretty uptime hostname # private DNS name hostname -i # private IP hostnamectl set-hostname "swiggy" # change hostname ip addr # show private IP ip route # show routing table ifconfig # show IP (older tool) date # current date timedatectl # show timezone timedatectl set-timezone Asia/Kolkata # set timezone to IST who # logged-in users whoami # current user ps # running processes kill -9 PID # kill a process # Date format examples date +"%d" # Day of month (01-31) date +"%m" # Month (01-12) date +"%y" # Last two digits of year date +"%H" # Hour (00-23) date +"%M" # Minute (00-59) date +"%S" # Seconds (00-60) date +"%D" # MM/DD/YY date +"%F" # YYYY-MM-DD date +"%A" # Day of week date +"%B" # Month name 
🔹 Hardware Commands
lscpu or cat /proc/cpuinfo # CPU architecture lsblk -a # block devices free or cat /proc/meminfo # memory details in KB free -m # memory details in MB df -h # disk usage (human readable) 
🔹 File Commands
touch filename # create file touch aws azure gcp # create multiple files touch linux{1..5} # create linux1..linux5 files rm filename # remove file with permissions rm -f filename # remove file forcefully rm -f aws azure gcp # remove multiple files rm -f linux{1..5} # remove multiple files rm -f * # delete all files rm -f *.txt # delete all .txt files rm -f a* # delete all files starting with "a" 
🔹 Folder Commands
mkdir foldername # create folder mkdir git maven jenkins # multiple folders mkdir docker{1..5} # docker1..docker5 rmdir foldername # remove empty folder rmdir git maven jenkins rmdir docker{1..5} rmdir * # remove all empty folders rm -rf * # remove all files & folders (including non-empty) 
🔹 Listing Files
ll # list files with details ls # list only names ll -t # sort by modification time ll -r # reverse order ll -a # include hidden files 
🔹 Changing Directory
cd foldername # change directory cd # go to root directory cd - # go to previous folder cd ../ # go one folder back cd ../../ # go two folders back 
🔹 Directory Operations
mkdir folder1/folder2 # create folder2 inside folder1 ll folder1 # list contents of folder1 touch folder1/aws.txt # create file inside folder1 mkdir -p aws/azure/gcp/devops # create nested folders automatically 
🔹 Copy & Move Commands
# Copy cp file1 file2 # copy file1 to file2 (overwrites) cat file1 >> file2 # append file1 into file2 safely # Move / Rename mv file1 file2 # rename/move file1 to file2 
🔹 Cat Command
cat filename # read file cat > filename # overwrite file cat >> filename # append to file 
🔹 Editors in Linux
Vim Editor (command, insert, save & quit modes) 
Nano Editor (simpler) 
Vim Basics:
Command mode:
gg / G / M / 4gg / :23 # navigation :set number # show line numbers yy / 4yy / p / 10p # copy & paste dd / 5dd # delete u / Ctrl+r # undo / redo /word or ?word # search word :%s/old/new/ # replace 
Insert mode:
i # insert A # end of line I # start of line O # new line above o # new line below 
Save & Quit:
:w # save :q # quit :q! # quit forcefully :wq # save & quit :wq! # save & quit forcefully 
🔹 Grep (Search)
grep "word" filename # search a word grep -n "word" filename # show line numbers grep -c "word" filename # count occurrences grep -i "word" filename # case-insensitive 
🔹 User Commands
cat /etc/passwd or getent passwd # list users useradd username # add user passwd username # set password userdel username # delete user (folder remains) userdel -r username # delete user & home folder useradd -M username # create user without folder su - username # switch user 
🔹 Group Commands
cat /etc/group # list groups groupadd group_name # add group groupdel group_name # delete group usermod -a -G group user # add user to group 
🔹 Permission Commands
chown username filename # change owner chgrp groupname filename # change group chown username:groupname file # change user & group chown -R username:groupname folder # change user & group recursively chmod 777 filename # change permissions 
🔹 Search Commands (Files & Folders)
Find:
find . -name file # find file in current dir find /proc/ -name filename # find file in /proc find . -type d -name folder # find folder find . -type f -name file1.txt # find file find . -type f -perm 777 # files with 777 permissions find . -type f ! -perm 777 # files not with 777 find / -user username # files owned by user find / -group groupname # files owned by group 
Locate:
locate filename 
Note: Update Linux DB before using locate.
Difference:
find searches based on path you specify. 
locate searches entire system database. 
