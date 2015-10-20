# GitHub Tutorial

_by <Issam Djadja>_

---
## Git vs. GitHub
* ###Git
 * On a private machine
 * Has version control which basically holds snapshots (`commits`) of your code. This is essential for saving the code you worked on.

* GitHub
 * Work is done on a private machine, but code is saved on the cloud. Cloud is just a server holding alot of peoples code.
 * It keeps track of your your snapshots (`commits`).
 * Web page where you can publish your git repositories (where your code work history is stored) and collaborate with other people.



---
## Initial Setup
In order to setup git on your workspace their needs to be a few steps you must follow.  
1) First, you have to tell Git your name so all your `commits` (snapshots) are labled properly. So you type `git config --global user.name "YOUR NAME"`. This must be typed with no spelling errors and replace **YOUR NAME** with your name.  
2) Next Git needs to know your email address associated with the commits you make. Typing `git config --global user.email "YOUR EMAIL ADDRESS"` would do just that. Replace **YOUR EMAIL ADDRESS** with your email.  
3) Now go to [GitHub](https://github.com/) and create an account.  
4) After make an account in [Cloud9](https://c9.io/web/sign-up/free)  
5) Next on your new cloud9 account create a new workspace.
6) On the nexwly created workspace copy and paste this into it `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` be sure to follow the steps given to you after you pasted the code and hit enter.  
7) Then you go back to your GitHub account 

* Hit the **settings** icon on the top right corner 
* click on **SSH keys** 
* click **add SSH Key**
* on the tile field and add the description for instance you may call it "PersonalHP computer"
* paste your given key into "key field"
* click **Add key**
* Conforim action with your **GitHub password** you created earlier.  

8) Next test the connection with the command `ssh -T git@github.com`
* Dont freak out but this warning will be seen `The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?` just type **yes**.  
9) Then you will witness `Hi username! You've successfully authenticated, but GitHub does not
provide shell access.`  
10) Congrats you created your own SSH key, give yourself some snaps for that. 




---
## Repository Setup



---
## Workflow & Commands