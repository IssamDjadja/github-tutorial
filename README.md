# GitHub Tutorial

_by Issam Djadja_

---
## Git vs. GitHub
* ###Git
 * On a private machine
 * Has version control which basically holds snapshots (`commits`) of your code. This is essential for saving the code you worked on.   
 * Does not require GitHub

* GitHub
 * Work is done on a private machine, but code is saved on the cloud. Cloud is just a server holding alot of peoples code.
 * It keeps track of your your snapshots (`commits`).
 * Web page where you can publish your git repositories (where your code work history is stored) and collaborate with other people.  
 * Requires Git 


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


1) Now go to [GitHub](https://github.com/)  

* Hit settings
* Click new repository  
* Create a message for your repository such as "Github-learning"  
 * If you want you can create a description but it's optional.
* Choose between public or private. 
* Hit the check mark that says **initialize this with a Readme**
* Lastly click **create repository**  

2) Now you want to create a remote. A remote sets up a connection between your private machine and github. This allows for your changes made on your machine to appear on your github website.  

* To add a remote you type `git remote add` and either an origin or url at the end. A remote can take two forms.
 * It can be the origin of which you are creating the remote which looks like this `git remote add origin https://github.com/user/repo.git`.
 * A url at the end of a remote is basically copying the url from your page to the end of `git remote add` but origin makes it so you don't have to keep typing the url if you know you will save your changes to the same place every time. 
 * The purpose for `git remote add origin` is to allow one to `git push origin master` and `git pull origin master`. To understand what each one does look at **Workflow & Commands**  
* If you type `git remote add origin https://github.com/user/repo.git` and you see (**fatal: remote origin already exists.**) then you tried adding a remote with the same name as an exsiting remote. 
 * To fix this you can change the name of the new remote, rename your old remote, or delete your old remote. **But be carefull with the last option**.


---
## Workflow & Commands
Now you are probably sitting there with an initialized file but wondering how to **add** content to your file.   
1) Write something on a created Readme file you have open.  
2) Then you will see a circle next to the readme which indicates you have unsaved work. Hit the **command key and S key** in order to save. On the middle left you will see in green text **changes saved**.  
3) Now if you type `ls` you shouldn't see the folder your Readme is in. If you don't then type `cd` `folder name` of the Readme file.  
4) Now you should be able to type `git add` `file name`. If you see an error then revert back to step three.   

* `git add` is like adding people to a photo before you actually take the photo.  

5) Then type `git status`. 

* You do this so you can verifiy if you have anything **added** or **commited**.  


6) Next type as follows with **no spelling mistakes**. `git commit -m "Your message here`. In the quotation marks type a brief message in the present tense of what you are saving. For instance if I added a picture to my file then my message is "Add picture to file". It sounds akward and you may be tempted to change it into the paste tense, but don't.  

* `git commit -m "Your message here"` is basically taking the picture of the people you decided to add to your photo. Once the photo is taken then everything you decided to add with the command `git add` is saved.  
* You should see something along the lines of this `1 file changed, 4 insertions(+), 3 deletions(-)`.

7) Assuming you made a remote correctly you should be able to push work to your github.

* Type `git push origin master`. 
 * This basically takes the `commit` you made and sends it directly to your github through the `remote` you created.
 * You should see some like this  
```Counting objects: 5, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 371 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To git@github.com:IssamDjadja/github-tutorial.git
   82e05ca..251a018  master -> master```.

8) Give yourself a lot of snaps because you did your first `git push`, `git status`, and  `git commit -m ""`.


---
##Error handling

 * Now I myself have accidently initialized a file that was not supposed to be initialized.If you want to remove a Git repository that was created on accident then you type in `rm -rf` and at the end of the command you type the **file name** you want to uninitialize.  
 * If you truly want to delete every single git repository leaving you with an **empty workspace** you enter `rm -rf .git`.  
 
---

##Collaboration

 * If you ever want to collaborate with someone or you want to take the code they worked on to learn from. You input `git clone [url]` command with the url of the project you want to replicate.  
  * `git clone [url]` can also be used for a last resort when the work you have saved on your private machine is deleted. 
 * **To clone**  
 1) Go to the repository you want to clone  
 2) Copy the SSH clone url  
![alt text](http://oi42.tinypic.com/2laznmb.jpg)   
 3) Go to your workspace  
 4) Input `git clone [url]`.The url should be the **SSH clone url**.  
 5) Then you should see something like this  
```Cloning into 'github-tutorial'...
remote: Counting objects: 25, done.
remote: Total 25 (delta 0), reused 0 (delta 0), pack-reused 25
Receiving objects: 100% (25/25), done.
Resolving deltas: 100% (6/6), done.
Checking connectivity... done.```  

 6) Now pat yourself on the back since you did your first clone. HUZZAH!

Now one day you probably cloned someones work. Then tried to make a commit on their work and tried pushing it through your remote only to encounter something like this  
```ERROR: Permission to bmuellerhstat/github-tutorial.git denied to IssamDjadja.
fatal: Could not read from remote repository.` 
Please make sure you have the correct access rights
and the repository exists.```

This happened because you useing `git clone` but were denied access to push work.
Instead you could use forking which basically creates a personal copy of someone's work. Forking as a bridge between someone's repository and your personal copy.
 
 **To fork somone's work**:  
 1) Go to there github page and click on the repository you want to fork.  
 2) On the top right corner hit fork.  
 ![alt text](https://github-images.s3.amazonaws.com/help/bootcamp/Bootcamp-Fork.png)  
 3) Then you will be on your github with their repository, so you go to the **SSH clone url**.     
 4) Copy it and go to your workspace.
 5) Now enter `git clone [urls]` with the url being the copied SSH key from step 3.  
 6) With the clone made try adding, commiting and pushing to your gihub.  
 7) If you did everything right then changes should be pushed to your forked repository on github.
 8) High five, you just forked and made changes to it.
 
 
 
 
 Remember the first Readme file you ever made. Lets try something crazy with it. Type `rm -rf`  and the file name (in this case Readme) at the end of the command without any questions.  
 If you listned to me then that selected file has been deleted.  
 Don't yell at me just yet, unless you don't have a copy on the cloud then you can yell.  
 If not type `git pull origin master`.
 
* You should see your work back.
 * `Git pull` is taking the file from your cloud and bringing it to yor local machine. Pretty much the exact opposite of `git push`.

But what if you wanted the creator to see the changes you made for the forked repository you made early. But wait, early I told you that you can't push work to the creator unless it's yours.

* Yes thats true, but you can make **pull requests**.
  * A **pull requests** is asking permission from the original creator of your forked repository to see changes you made.
 
To make a pull request:  
1) Go to the repository you forked
2) Click **compare and pull request**   
 ![alt text](http://i.stack.imgur.com/8jEby.png)  
3) Next add a description of the changes you want the oringial creator to notice and click **create pull request**  
 ![alt text](https://help.github.com/assets/images/help/pull_requests/pull-request-click-to-create.png)  

4) Now you have sent your very first pull request, Give yourself a lot of snaps.

* Note don't be discouraged if the changes you made are not added. The creator has the right to reject your request even though you thought it was a good change.



# github-tutorial-
