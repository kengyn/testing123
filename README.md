# How to use different git users on the same computer
## First, 
### 1. create ssh keys
### 2. add ssh key(s) to github account(s)
### 3. modify ssh config
[editor of choice] ~/.ssh/config
------------------------------------------------
	Host github.com
		Hostname github.com
		User git
		IdentityFile ~/.ssh/id_personal
	Host bruhub.com
		Hostname github.com
		User git
		IdentityFile ~/.ssh/id_work
------------------------------------------------
### 4. clone using git user u want
  git clone git@bruhub.com:[ur actual git username]/[ur actual repo].git

### 4-1. modify existing repo
  git remote set-url origin git@bruhub.com:[ur actual git username]/[ur actual repo].git

### 5. set user for curr repo
  git config user.name "[name]"
  git config user.email "[private email found in github settings/emails/keep my email addresses private checkbox description]"
  ***might or might not need to set ssh here too***
  git config user.signingkey path/to/.ssh/ssh.pub 
 ***if u already commmited with the wrong author***
  git commit --amend --reset-author --no-edit



