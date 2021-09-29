# Connect SSH
### Connect to server via SSH
- `ssh -i <secret_key> <user>@<ip_or_host>`

### Copy file from server
- `scp -i <secret_key> <user>@<ip_or_host>:<path_to_file_on_server> <path_to_file_on_local>`

# MySQL
### Connect MySQL
- `mysql -u<user> -p -h <ip_or_host>`

### Export database
- `mysqldump -u<user> -p -h <ip_or_host> <database> > <path_to_file>.sql`

### Export table in database
- `mysqldump -u<user> -p -h <ip_or_host> <database> <table> > <path_to_file>.sql`

# Create SSH Key
### Windows
#### Generating a new SSH key
- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

#### Adding your SSH key to the ssh-agent
- `eval $(ssh-agent -s)`
- `ssh-add ~/.ssh/id_rsa`

#### Add the SSH key to your GitHub account
1. Copy the SSH key to your clipboard.
  - `cat ~/.ssh/id_rsa.pub`
  - `# Copies the contents of the id_rsa.pub file to your clipboard`

2. In the upper-right corner of any page, click your profile photo, then click Settings.
3. In the user settings sidebar, click SSH and GPG keys.
4. Click New SSH key or Add SSH key.
5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6. Paste your key into the "Key" field.
7. Click Add SSH key.
8. If prompted, confirm your GitHub password.

### Linux
#### Generating a new SSH key
- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

#### Adding your SSH key to the ssh-agent
- `eval "$(ssh-agent -s)"`
- `ssh-add ~/.ssh/id_rsa`

#### Add the SSH key to your GitHub account
1. Copy the SSH key to your clipboard.
  - `cat ~/.ssh/id_rsa.pub`
  - `# Copies the contents of the id_rsa.pub file to your clipboard`

2. In the upper-right corner of any page, click your profile photo, then click Settings.
3. In the user settings sidebar, click SSH and GPG keys.
4. Click New SSH key or Add SSH key.
5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6. Paste your key into the "Key" field.
7. Click Add SSH key.
8. If prompted, confirm your GitHub password.

### Mac
#### Generating a new SSH key
- `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

#### Adding your SSH key to the ssh-agent
- `eval "$(ssh-agent -s)"`
- `open ~/.ssh/config`
- `touch ~/.ssh/config`
- Open your ~/.ssh/config file, then modify the file, replacing ~/.ssh/id_rsa if you are not using the default location and name for your id_rsa key.
  ```
  Host *
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ~/.ssh/id_rsa
  ```
- `ssh-add -K ~/.ssh/id_rsa`

#### Add the SSH key to your GitHub account
1. Copy the SSH key to your clipboard.
  - `pbcopy < ~/.ssh/id_rsa.pub`
  - `# Copies the contents of the id_rsa.pub file to your clipboard`

2. In the upper-right corner of any page, click your profile photo, then click Settings.
3. In the user settings sidebar, click SSH and GPG keys.
4. Click New SSH key or Add SSH key.
5. In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".
6. Paste your key into the "Key" field.
7. Click Add SSH key.
8. If prompted, confirm your GitHub password.

# Disable SELinux Permanently
`vi /etc/sysconfig/selinux`  
`SELINUX=disabled`  
`sestatus`  

# Change Port on Centos
`firewall-cmd --get-active-zones`  
`firewall-cmd --zone=public --add-port=80/tcp --permanent`  
`firewall-cmd --zone=dmz --add-port=80/tcp --permanent`  
`firewall-cmd --reload`

# Extend ổ cứng trên centos
- fdisk /dev/sda;
- Nhấn d - > 2
- Nhấn n - > p -> 2 , sau đó enter 2 lần
- Nhấn w
- reboot;
- Đăng nhập lại:
- pvresize /dev/sda2;
- lvextend /dev/mapper/centos-root -l +100%FREE;
- xfs_growfs /dev/mapper/centos-root;
Xong.  
Kiểm tra lại chạy: lsblk
