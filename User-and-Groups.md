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

# when a new user is created, all files in /etc/skel gets copied to home directory of the user

# Set a password for user
sudo passwd john