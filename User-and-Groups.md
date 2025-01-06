
###
# USERS
###

# Check user and system users in the system
cat /etc/passwd

# Adding new user with home directory
sudo useradd -m john

# create a user with diff shell
sudo useradd -s /bin/othershell john

# create a user with diff home directory location
sudo useradd -md /home/othedirectory john

# create a user with diff UID
sudo useradd -u 5001 john

# create a system account
sudo useradd -r



# Deleting any user with their home directory
sudo userdel -r john



# Change user's login name
sudo usermod -l jane john

# Change user's login shell
sudo usermod -s /bin/othershell john

# Lock a user's account
sudo usermod -L john

# Unlock a user's account
sudo usermod -U john

# User's account will expire
sudo usermod -e 2030-12-30 john

# Remove user's expiry date on account
sudo usermod -e "" john



# Set a password for user
sudo passwd john

# Expire user's password instantly
sudo chage -d 0 john

# Cancel user's password change
sudo chage -d -1 john

# User will need to change password every 30 days
sudo chage -M 30 john

# Password never expires
sudo chage -M -1 john

# Show details of user's password
sudo chage -l john



###
# GROUPS
###

# Check all groups in the system
cat /etc/group

# Create new group
sudo groupadd test

# add user to group
sudo gpasswd -a john test

# remove user from group
sudo gpasswd -d john test

# change user's primary group
sudo usermod -g john test

# Change group's name
sudo groupmod -n ok test

# Delete Group
sudo groupdel test

# use gpasswd to add users to group because user just gets added to the group without removing other groups associated with the user.
# usermod will change user, thats why, if this is being used to add user to a group, it will remove existing groups.


# in the shell, to change variable. HIST = 1000
# Once you close the shell, its gone.

# To save just for the user, put it in .bashrc file

# to make sure every user has a new environment variables, add this to /etc/environment

# run a command everytime user logs in /etc/profile.d/lastlogin.sh

# when a new user is created, all files in /etc/skel gets copied to home directory of the user 
