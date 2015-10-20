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
* Click on **SSH keys** 
* Click **add SSH Key**
* On the tile field add the description. For instance you may call it "PersonalHP computer"
* Paste your given key into "key field"
* Click **Add key**
* Conforim action with your **GitHub password** you created earlier.  

8) Next test the connection with the command `ssh -T git@github.com`  

* Dont freak out but this warning will be seen `The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?` just type **yes**.   

9) Then you will witness (`Hi username! You've successfully authenticated, but GitHub does not
provide shell access.`)  
10) Congrats you created your own SSH key, give yourself some snaps for that. 

---
## Repository Setup
The `git init` command creates a brand new git repository. This may be used to transform a known project into a Git repository. This is the very first command you type in **in order to use any other Git command**. All in all typing `git init` adds **.git** to your file making it possible to track changes to it.  

* Now I myself have accidently initialized a file that was not supposed to be initialized.If you want to remove a Git repository that was created on accident then you type in `rm -rf` and at the end of the command you type the **file name** you want to uninitialize.  
* If you truly want to delete every single git repository leaving you with an **empty workspace** you enter `rm -rf .git`.  

Now you are probably sitting there with an initialized file but wondering how to **add** content to your file.   
1) Write something on a created Readme file you have open.  
2) Then you will see a circle next to the readme which indicates you have unsaved work. Hit the **command key and S key** in order to save. On the middle left you will see in green text **changes saved**.  
3) Now if you type `ls` you shouldn't see the file your Readme is in. If you don't then type `cd` `folder name` of the Readme file.  
4) Now you should be able to type `git add` `file name`. If you see an error then revert back to step three.   
* `git add` is like adding people to a photo before you actually take the photo.  
5) Next type as follows with no spelling mistakes. `git commit -m "Your message here`. In the quotation marks type a brief message in the present tense of what you are saving. For instance if I added a picture to my file then my message is "Add picture to file". It sounds akward and you may be tempted to change it into the paste tense, but don't.

* `git commit -m "Your message here"` is basically taking the picture of the people you decided to add to your photo. Once the photo is taken then everything you decided to add with the command "git add" is saved.  

6) Now go to [GitHub](https://github.com/)  

* Hit settings
* Click new repository  
* Create a message for your repository such as "Github-learning"  
 * If you want you can create a description but it's optional.
* Choose between public or private. 
* Hit the check mark that says **initialize this with a Readme**
* Lastly click **create repository**  

7) Now you want to create a remote. A remote sets up a connection between your private machine and github. This allows for your changes made on your machine to appear on your github website.  

* To add a remote you type `git remote add` and either an origin or url at the end. A remote can take two forms.
 * It can be the origin of which you are creating the remote which looks like this `git remote add origin https://github.com/user/repo.git`.
 * A url at the end of a remote is basically copying the url from your page to the end of `git remote add` but origin makes it so you don't have to keep typing the url if you know you will save your changes to the same place every time. 
 * The purpose for `git remote add origin` is to allow one to `git push origin master` and `git pull origin master`. To understand what each one does look at **Workflow & Commands**  
* If you type `git remote add origin https://github.com/user/repo.git` and you see (**fatal: remote origin already exists.**) then you tried adding a remote with the same name as an exsiting remote. 
 * To fix this you can change the name of the new remote, rename your old remote, or delete your old remote. **But be carefull with the last option**.
---
## Workflow & Commands
