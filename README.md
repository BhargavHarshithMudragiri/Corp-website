# corp-website
How to create Git Repository in Git Server ?
First create a VM with ubuntu 22.04 and SSH key in Azure
Once SSH pem key is downloaded convert it to ppk file using puttykeygen
Login to VM and authenticate using ppk file
Become root user using Sudo su -
Check the availability of Git using git --version
To convert VM machine to git server create a git folder using command mkdir -p /srv/git/projects/<projectname.git>
Give write permissions to the folder using chmod -R ugo+rwx /srv/git/projects/<projectname.git>
Now create user called git using adduser git
Become user git using su git
Go to git home directory using cd
create one folder named .ssh using mkdir .ssh and give permissions using chmod 700 .ssh
Now create one file named authorized_keys in .ssh folder using touch .ssh/authorized_keys
Give permissions to the file using chmod 600 .ssh/authorized_keys
From Developer Laptop ,copy the newly created ssh-pubkey to file .ssh/authorized_keys in git server
Now change the directory to git repo using cd /srv/git/projects/<projectname.git>
Initialize git using git init --bare
