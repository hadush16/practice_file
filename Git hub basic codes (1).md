Github basic codes

**Installing Git**  
**Windows Install**  
Download Git For Windows Find the downloaded .exe file and open it to execute Git Bash.   
**Configuring Git**

- [ ] git config \--global user.name "hadush16"  
- [ ] git config \--global user.name "hadush12brhane@gmail.com"  

Committing The most important Git feature\! 

- [ ]  git status  
- [ ]  git init   
- [ ]  git add file1 file2  
- [ ] Git commit \-m “ “  
        
      DO NOT INIT A REPO INSIDE OF A REPO\! Before running git init, use git status to verify that you are not currently inside of a repo.  
        
      Atomic Commits When possible, a commit should encompass a single feature, change, or fix. In other words, try to keep each commit focused on a single thing. This makes it much easier to undo or rollback changes later on. It also makes your code or project easier to review.   
      Ignoring Files  
       Create a file called .gitignore in the root of a repository. Inside the file, we can write patterns to tell Git which files & folders to ignore: .DS\_Store will ignore files named .DS\_Store folderName/ will ignore an entire directory \*.log will ignore any files with the .log extension  
      Git Branching   
      Branches are an essential part of Git\! Think of branches as alternative timelines for a project. They enable us to create separate contexts where we can try new things, or even work on multiple ideas in parallel. If we make changes on one branch, they do not impact the other branches (unless we merge the changes)     
      Master? Main? In 2020, Github renamed the default branch from master to main. The default Git branch name is still master, though the Git team is exploring a potential change. We will circle back to this shortly.   
* git branch view of \=\>  branches  u are currently on  
* git branch \<branch name\>  creating of branches   
* git switch  \< branch name\>  
* git checkout \< branch name\>  
*  git switch \-c \< branch name\>  
* git branch \-v \=\> v flag with git branch to view more information about each branch

Merging  
To merge, follow these basic steps: 

1.  Switch to or checkout the branch you want to merge the changes into (the receiving branch)   
2. Use the git merge command to merge changes from a specific branch into the current branch.  
   1. git switch master   
   2.  git merge bugfix 

Resolving Conflicts  
Whenever you encounter merge conflicts, follow these steps to resolve them: 

1. Open up the file(s) with merge conflicts   
2. Edit the file(s) to remove the conflicts. Decide which branch's content you want to keep in each conflict. Or keep the content from both.   
3. Remove the conflict "markers" in the document   
4. Add your changes and then make a commit\!   
   1. git branch \-d bugfix deleting \=\> the branch

Git Diff  
 We can use the git diff command to view changes between commits, branches, files, our working directory, and more\! We often use git diff alongside commands like git status and git log, to get a better picture of a repository and how it has changed over time.

* git diff \--staged   
*  git diff \--cached   
* git diff branch1..branch2  \=\>Comparing Branches  
* git diff commit1..commit2 \=\> Comparing Commits

Stashing   
Git provides an easy way of stashing these uncommitted changes so that we can return to them later, without having to make unnecessary commits. 

*  git stash=\> Now that I have stashed my changes, I can switch branches, create new commits,   
* git stash pop   
* git stash apply to apply whatever is stashed away,  
* git stash \-u=\> to tell git stash to include those untracked files.  
* git stash apply stash@{2}   
* git stash drop stash@{2}   
* git stash clear 

**Undoing Stuff & Time Traveling**  
**![][image1]**

- [ ] git switch \-c newbranch  
      While in detached HEAD, make a new branch and switch to it. Head is now back to pointing at a branch reference\!  
- [ ] git checkout HEAD\~1  
      HEAD\~1 refers to the commit before HEAD (parent) HEAD\~2 refers to 2 commits before HEAD (grandparent)  
      

      ### **What’s happening**

* You checked out a **specific commit** (`036cc3b`) instead of a branch.

* That’s why Git says:

   "HEAD detached at 036cc3b"

In this state, **new commits won’t be linked to any branch** — they’ll just “float” until you create a branch.

#### **Option 1: Go back to your main branch**

If you just want to return to your main branch:

`git switch main`

or (if your main branch is called `master`)

`git switch master`

Then check:

`git status`

Now your HEAD should no longer be detached.

#### 

#### **Option 2: Keep your current changes (create a new branch from this commit)**

If you want to **continue working from commit `036cc3b`**:

`git switch -c new-branch-name`

Example:

`git switch -c fix-detached-head`

Now your new branch `fix-detached-head` starts from that commit, and you can commit safely.

#### **Option 3: Undo and go back to the previous state**

If you just want to go back to where you were before:

`git switch -`

### **Discarding Changes**

- [ ] git checkout HEAD \<file\>  
- [ ] git checkout \-- \<file\>  
      

**Restore**  
To restore the file to the contents in the HEAD, use git restore 

- [ ] git restore \<file-name\>  
- [ ] git restore \--source HEAD\~1 index.html  
- [ ] git restore \--staged \<file-name\>

**Git Reset**   
git reset will reset the repo back to a specific commit. The commits are gone

- [ ] git reset \<commit-hash\>  
      ![][image2]  
      

**git revert**  
 If you want to reverse some commits that other people already have on their machines, you should use revert. If you want to reverse commits that you haven't shared with others, use reset and no one will ever know\! 

- [ ] git revert \<commit-hash\> 

                         

| Git  | Github |
| :---- | :---- |
| Git is the version control software that runs locally on your machine. You don't need to register for an account. You don't need the internet to use it. You can use Git without ever touching Github. | Github is a service that hosts Git repositories in the cloud and makes it easier to collaborate with other people. You do need to sign up for an account to use Github. It's an online place to share work that is done using Git.  |

**Collaboration**   
If you ever plan on working on a project with at least one other person, Github will make your life easier\!  
**Cloning**

- [ ] git clone\<url\> 

**Permissions?** Anyone can clone a repository from Github, provided the repo is public.   
Register to Github

SSH Keys

1. Open terminal  
2. Enter ls \-al \~/.ssh

           See  \#lists the file

###  **1\. Open Git Bash or PowerShell**

You can use **Git Bash** (installed with Git) or **Windows PowerShell**.

---

### **🔑 2\. Generate a new SSH key**

Run this command (replace your email address):

`ssh-keygen -t ed25519 -C "your_email@example.com"`

If your system doesn’t support `ed25519`, use:

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

---

### **💾 3\. Save the key**

When prompted:

`Enter a file in which to save the key (/c/Users/YourName/.ssh/id_ed25519):`

Just press **Enter** to accept the default location.

Then you’ll be asked for a passphrase (optional but recommended).  
 If you don’t want one, press **Enter** twice.

---

### **🔍 4\. Start the SSH agent**

`eval "$(ssh-agent -s)"`

---

### **➕ 5\. Add your private key to the SSH agent**

`ssh-add ~/.ssh/id_ed25519`

---

### **📋 6\. Copy your public key**

To copy it to your clipboard:

`clip < ~/.ssh/id_ed25519.pub`

Now your SSH key is copied\!

---

### **🌐 7\. Add the SSH key to your GitHub account**

1. Go to **GitHub → Settings → SSH and GPG keys**

2. Click **New SSH key**

3. Paste the key into the field

4. Give it a title (e.g., “My Windows Laptop”)

5. Click **Add SSH key**

---

### **✅ 8\. Test the connection**

Run:

`ssh -T git@github.com`

If you see something like this:

`Hi username! You've successfully authenticated, but GitHub does not provide shell access.`

🎉 You’re done\!

**Remote**

### **…or create a new repository on the command line**

1. echo "\# marketing" \>\> README.md  
2. git init  
3. git add README.md  
4. git commit \-m "first commit"  
5. git branch \-M main  
6. git remote add origin https://github.com/hadush16/marketing.git  
7. git push \-u origin main

### **…or push an existing repository from the command line**

1. git remote add origin https://github.com/hadush16/marketing.git  
2. git branch \-M main  
3. git push \-u origin main

    
     **Delete the local branch**

If you just want to delete the branch on your computer:

`git branch -d dogs`

If Git says the branch is not fully merged and refuses, force it:

`git branch -D dogs`

## 

## **☁️ Delete the remote branch (on GitHub)**

If you want to delete it **from GitHub**, use:

`git push origin --delete dogs`

✅ That removes the `dogs` branch from your GitHub repository.

---

## **🔍 To confirm it’s gone:**

Check local branches:

 `git branch`

* 

Check remote branches:

 `git fetch -p`

* `git branch -r`

## **`To remove the submodule properly`**

### **`🪜 Step-by-step:`**

`1️⃣ Deinitialize the submodule`

`git submodule deinit -f flutter-complete-guide-course-resources`

`2️⃣ Remove the submodule entry from the index`

`git rm -f flutter-complete-guide-course-resources`

`3️⃣ Delete the submodule’s files`

`rm -rf .git/modules/flutter-complete-guide-course-resources`

`4️⃣ Commit the changes`

`git commit -m "Removed submodule flutter-complete-guide-course-resources"`

`5️⃣ Push to GitHub`

`git push origin main`

`🔁 Replace main with your actual branch name if different.`

---

`✅ Done`

Git Fetch 

1.  git fetch \<remote\>  
2.  git fetch  \<remote\>  \<branch\>  Ex: git fetch origin master  
3. git checkout \<origin/branch\>  or  \--track origin/puppies 

Git Pulling  
git pull \= git fetch \+ git merge   
 **git fetch**  
 update the remote tracking branch with the latest changes from the remote repository  
 **git merge**   
update my current branch with whatever changes are on the remote tracking branch

1.  git pull  \<remote\> \<branch\> Ex: git pull origin master  
   

An even easier syntax\! If we run ***git pull*** without specifying a particular remote or branch to pull from, git assumes the following: remote will default to origin branch will default to whatever tracking connection is configured for your current branch.

### GitHub – Summary

#### 🏛️ Public vs. Private Repositories

* **Public Repos: Visible to everyone on the internet; anyone can view them.**

* **Private Repos: Only accessible to the owner and invited collaborators.**

---

#### **🗑️ Deleting GitHub Repositories**

* **Only the repo owner (or those with the right permissions) can delete a repository.**

---

#### **👥 Adding Collaborators**

* **You can invite others to work on your private repositories.**

* **Collaboration allows multiple users to push, pull, and review code together.**

---

#### **📘 README Files**

* **Used to describe important details about a project:**

  * **What it does**

  * **How to use it**

  * **Why it’s important**

  * **Who maintains it**

* **Filename: `README.md` (written in Markdown)**

* **GitHub automatically displays it on the repo’s homepage.**

---

#### **✍️ Markdown Basics**

* **Simple syntax for formatting text in README files.**

* **Supports:**

  * **Headings (`#`, `##`, `###`, etc.)**

  * **Bold/italic text**

  * **Lists and links**

  * **Code blocks**

  * **Images**

---

#### **📄 GitHub Gists**

* **A lightweight way to share code snippets or small notes.**

* **Easier to create than full repositories, but with fewer features.**

---

#### **🌐 GitHub Pages**

* **Lets you host static websites (HTML, CSS, JS) directly from a GitHub repository.**

* **No server-side code (like Python or Node) is supported.**

**Types of GitHub Pages:**

1. **User Site: One per GitHub account (e.g., `username.github.io`).**

2. **Project Site: One per repository (e.g., `username.github.io/repo-name`).**

---

### **✅ In Short**

**GitHub is not just for storing code — it’s also a collaboration, documentation, and publishing platform.**  
 **It allows version control, teamwork, public or private sharing, and even simple website hosting.**

**git workflows (for collaboration)**   
**Centralized Workflow**

1. Hadush clones the repo Ex master   
2. Zereu clones the same repo Ex master   
     
1. Hadudsh gets to work on a new feature\! Adding and Committing all day long\!  
2. Hadush now pushes up his new work to Github  
3. Zereu has also been hard at work on her own new feature.  
4. He tries to push her new work up to Github, but she runs into trouble\! As he is behind the master branch   
- [ ] Git push origin master 

      **Fix** 

* So he pulls to get the changes from origin master Forrest's work must be merged in. Hopefully this goes relatively smoothly\!  
- [ ] Git pull origin master  
- [ ] Git commit \-m “ merged “  
* Now that she has merged the latest work from Github, she can push her master branch up\!  
- [ ] Git push origin master   
        
        
      **The Problem**

      **Frequent merge conflicts:** Everyone edits the same branch, so conflicts happen often.  
      **Unstable main branch:** If someone pushes buggy or incomplete code, it affects everyone.  
      **No room for experimentation:** Developers can’t safely test new features without impacting others.  
      **Difficult collaboration:** Working together on the same branch leads to broken code and wasted time.  
      

**Enter Feature Branches**

 Rather than working directly on master/main, all new development should be done on separate branches\!. 

1. Hadush clones the repo Ex master   
2. Zereu clones the same repo Ex master  
- [ ] Hadush starts work on a new feature. He does all this work on a separate branch\!  
- [ ] Hadush wants Zereu to take a look at his new feature. Instead of merging it into master, he just pushes his feature branch up to Github\!  
* Git status  
* Git add index.html  
* Git commit \-m “  “  
* Git remote \-v   
* Git push origin \<H feature branch\>  
*   
- [ ] Zeru hears from Hadush that he wants her to take a look at his new work. She pulls down his feature branch from Github.  
* Git pull origin \<main/master \>  
* Git git switch \-c \<Z feature branch\>  
* Git status   
* Git add index.htm  
* Git commit \-m “ “  
* Git push origin  Z feature branch  
* Git fetch origin master   
* Git branch \-r  
* Git checkout origin/H feature branch  
* Git switch \<H feature branch\>  
* Git add index.html  
* Git commit \-m “edited H feature branch”  
* Git push origin \<H feature branch\>  
* Git switch origin \<Z feature branch\>




  * Git pull origin \<h feature branch\>  
  * Git log  
  * Git add …  
  * Git commit \-m “jj”  
  * Git push origin \<H feature branch\>

    

- [ ] Zereu takes a look at the code and makes a couple improvements of his own. He adds/commits on the H feature branch and push to the H feature branch  

      

- [ ] Hadush fetches from Github and sees that there is new work on the \<H feature branch\> branch. He pulls the changes down and continues work.  
      * Git pull origin \<H feature branch\>        
- [ ] Hadush decides he is happy with the new feature, so he merges it into master\! Think as project owner  
      * Git status  
      * Git switch origin main  
      * Git pull origin main  
      * Git merge \<h feature branch\>  
      * Git status  
      * Git push origin main   
- [ ] Zereu takes a look at the code and makes a couple improvements of his own  
      * Git status   
      * Git switch main  
      * Git pull origin main

**Merging In Feature Branches**

* git fetch origin \<main\>  
* git switch my-new-feature   
* git merge master   
* fix conflicts\!  
* git switch master   
*  git merge my-new-feature   
* git push origin main


  

**Forking Github**  
 (and similar tools) allow us to create personal copies of other peoples' repositories. We call those copies a "fork" of the original. When we fork a repo, we're basically asking Github "Make me my own copy of this repo please" As with pull requests, forking is not a Git feature. The ability to fork is implemented by Github.   
![][image3]

* Git status  
* Git clone \<url\> for the my fork  
- [ ] Git remote add upstream \<url of original\> for update  
- [ ] Git remote \-v to see the list of two    
- [ ] Git pull upstream main to get updates from the original to my forked

**Rebasing vs merging**  
 There are two main ways to use the git rebase command:- 

1. as an alternative to merging  
* Git merge master  
* Git rebase master  
* Git rebase \--continue   
     
2. as a cleanup too

**Git Tags**  
**Viewing Tags** git tag will print a list of all the tags in the current repository.

- [ ] git tag   
- [ ] git tag \-l "\*beta\*"   
- [ ] git checkout  Checking Out Tags  
      * git tag \<tagname\> to create a lightweight tag,   
      * ❯ git tag \-a \<tagname\>  we can also use the \-m option to pass a message directly 

Tagging Previous Commits So far we've seen how to tag the commit that HEAD references. We can also tag an older commit by providing the commit hash: 

- [ ] git tag \-a  \<tagname\>  \<commit-hash\>  
- [ ] git tag \-d  \<tagname\>      to delete  
- [ ] git tag \-f \<tagname\>        to force  
- [ ] git push \--tags to push tags   
        
        
      **HASHING FUNCTIONS**  
        
- [ ] **echo 'hello' | git hash-object \--stdin \-w**  
- [ ] **git cat-file \-p \<object hash\>**  
*    **$Ex.  git cat-file \-p 5ff7e655a8ecb969bcfb912f0853d14e122d56fd**  
* **git cat-file \-p a224f Output  \=\>Wellcome**


**Git Reflog**  
The git reflog command accepts subcommands show, expire, delete, and exists. Show is the only commonly used variant, and it is the default subcommand. git reflog show will show the log of a specific reference (it defaults to HEAD). For example, to view the logs for the tip of the main branch we could run git reflog show main. 

- [ ] git reflog show HEAD

**Timed References**

- [ ] git reflog master@{one.week.ago}  
- [ ] git checkout bugfix@{2.days.ago}  
- [ ] git diff main@{0} main@{yesterday} 

**\=\> Code .     is the code use to open the vs code** 

**Git reset \- \- hard \<hash\>**  
**Reflogs Rescue**   
**W**e can sometimes use reflog entries to access commits that seem lost and are not appearing in git log.  
**Git Aliases**   
Global Git Config Git looks for the global config file at either \~/.gitconfig or \~/.config/git/config. Any configuration variables that we change in the file will be applied across all Git repos. We can also alter configuration variables from the command line if preferred  
**Adding Aliases** We can easily set up Git aliases to make our Git experience a bit simpler and faster. For example, we could define an alias "git ci" instead of having to type "git commit" Or, we could define a custom git lg command that prints out a custom formatted commit log

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAnAAAAFJCAYAAAAbjhBbAABXUklEQVR4Xu2dPY80u3HvJ1Ki5AQKHFwlhnBwgFam2AIECNANOlBmwIkSZWPYgCNlJ3HQNqBAmeDoBH0AQ5k/wTq6X2tuF1+axXohu3tmdnt2/wv8nmeabJJVxSJZw36Zyw1/+MMf/vCHP/zhD38v9XeRCfjDH/7whz/84Q9/+Dv332X5o38AAAAAAMDroBIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuVAAAAAAAAzo1KAAAAAAAA5+Zy+9l/X25/9weVAQB4IP/xw+X2z7/Q6cT4b5fb//7n5TYYeVvKe1CZXr3P5EjbJLNM2wqV/fGfdHqPI21m28r0M/DPi1z/+0PhP4RN3sUvvv2H2+W//0Wn38t//9ft8pd/1OlNFln+tJT5VqYD8NI8JoD7u6WO/5P42Z11fSXI9tlumZ828og9ffXNX+qyMr8HL/+z3+r81+aXt9/96m+3//m//y/wx5/L/MTP/3z73svbyPBP7QWzF8D1ynu8y0Ld4EjbR4IpXnZvAJdtK9N7nDWAs3xpEIH/0/3it/8SAy2Z/ggOBXALf/j3pezCp5vHwBfm/gDuJ0vZn+ZvNsv/P1sW/W/YN50qAPlLHQh4QQo/56d/qgNE4iesvJT9//wp/i+DFylHqGOR8xuqn/gL08ORj87LbW/i21jmZ436ua168PMt3SU/ZXakfuJtyfLBXsl2sjyVJf23yvp9CIr+XNKWIIiCpL9+98uU9vt0Tg3PL59ZHb/6fTn+5ve3P7IALJT/9Z9vf/w1r6fmr7/+1/T5l+G8/1mOf/dNzPsu/V+zyLmcd28ARwvmf/xGp2esRXdP+SMcCXYeidf2ewdwn822H9l24Nt/jEHWGQOlEFj+O3biwGdBL+S7+G1c2OkzBUJroMPq459/8tsUjKVAodc2BW8UbPHA5yff+gEcnW8GWBRIJTk5VH4NFtM5XpAjZd8ClV+Pnfq3BkUhkGW6St27fMt0NcqvQa1Fkn3rLlwOzvLx734lA7TId99RAPbn2+9UHb9f0v92+yMPqngA982/3v5KbSzH361lfnn77uf/GtqS7WTW8iGgtNqtoR2673/++7sCuC27Z60Abkv5I3z0Qu+1/Z4B3Ge07Ue2HfjTErz96R90+lk4u3wAbKcs5HmXhXaM+Ek5P++C8V2oHFSE/1M61eMFcATfzZFBhGRPfq5XnhMwArhwvghaQsDI9Jft54DSDXSM+nmaVf+mAI7kF+1K2bp8q4NHbrt86dbECD5bfL8ER9//KgdwtNu2BEJLMCQDq3YAFwO0NY0FcHn3rARvok4R6OUALLcfAkpet8XSHu3YfUfy3xHAeTs8P/4Q70/6cQne/rkRwFnlh9+U8lRuZIFICAZzHvFvur4qPzGyc3rw9nnblFe1L9re0j7lU2CV6yf78PIyOOEBS/4sy1t2zedvsa2pG3HEtr9YzvvPkiflC0FlyqN713he0za/0O1m6N7JnuyhbUP3XZeJvd23sPP1L+XSKgVQ4VIou0eOyv6FLnP+V+QPf1/XQYFXzlMBWKrvD6l+8xwuC3bhwKcgLuTrrlnaZZI7NWtglBbyvPDTZbcciOUAoBfA8Tp6QUgIeBqBw1o+7QR651kBnHXJMAeBWRcpXyizMYDbWn/etaR7B716yQ5y90vK1oSCNxFMStupMgwqKwP7FhTA/e7nKTCjwIsuVX63L4Cj8tUuHAvgKLhzg6rUHgV3sf4SrMUy8fLtX7/7fXUPXB0MxqAztn1HAPebuACqAOI3JXBYF03nPCs9LO4byoeb2Y2Fmji8U0My/VDa//EHu23CazuUc9pegzA6TrrxIEuWkwEcl42CGiovywQs2wrdsm0t3Q7ZNtXPAy9qQwaIIS/Jztvo2abZNsOU3dF9VwDnBUc8cAtB3nJODrrWKyDL8W9T0ObVQ/zFCs5yAJfSc3sykOTnmnkAvBQpiGjsOsljvguVAze+OxQW+1YAx+qUdVuES5cUDOUgR+4i0e4f5bUGpBHAmW2LQJCf89MUfDXb2Vl/pnl5lmQ30s36Jam9gBXA9WyXyy9l5f17LUIAlwKffEmTgqldARy7Ty0EV1UAJy6vcsKuW6wztP3rv6U6flkCshC00eXRJA+VYbLVO3THAzhaKOUCm9P5sXcJ1SsvF1/vUqC5UCe2LPQWsk6vbcJrm/DaJrnkMT9XlpMBnMzfY1upG0H6ybLeuRlLjrWMIYtXLu/G5R28nm28NIklu5W2+wGP8KCA8eRp3oGjz2sA9/cxGLPmHm8nj2gFcPJY7uJ18wB4KXQg0DvOu2IUuFGwRot/DuTCMQUFrQAuBVO5nMrvwO9zW8unOs0AiDACuK07ZHvly2ypv4LZZU2jwM7R6YhsZqBu2MbC0scjBnBxp4zvhu0L4OLnEExRHb0duBC4/S2UpQDt+5/nQC7tpv08X3JNgaG4hJrlWHftJM4l2xbeQioXYivIoAXVKy/TvSDKWpQzWxZ6C1nOa5vw2ia8tqVtZHuy3KYA7of6MqZnW6v8IwM4SvfK5B23KqgUu2I923hpEkt2q9zuAM7bOdsSwIVLpPSU6N+/TwBn1Q3Aa6EDgd4xX8hDQEIBVQpMwg5Z+pwDFRlk8CBG1r0Ffr9WVb4ViBh5R+6B28OWe+AqjN0569Jp5ohsrm5kn05dRwK4eKkyBm1HA7j1kiftpLXugVsDuBigff+rEvCFnbjlOJ+/BoWsvDzmsqhgcQu/8e8rkwuxCuDSwu2Vl4uvKp+wFuqMtWBvQQYhXtuE1zbhtS1tI+WsyuVLko0ATtmgYVupG0H6WbqpekU9Uo61jGMrq9x77sB5uu8K4LzAqxvAiYDLq4e4N4DzgkwAXg8dCFjH+R4putQnLyPSwr4GQd/qS228LroMye+hk21J6MnWqr5vY5l8rMrTjpVVnxHA5fJbn0I9ApfVqn+9HJz0qgLKdL65W5fqbsom+oJsL+9t5OWpX6v6WPm9l49zAMfTjgdwl/U1JPLhhP/59Z/X14CUAE4/9Zp31db6UvlVHnEJVcpyJICjRVKmZWhhHH+RPqdFmi/s3g5Rhs7PL/Vdb2o3AgNroZZ5skyPHFTk9n/8wW6b8NrOeVaZXpCSy4V7tMhOLD8EIT8U29I51T1xl7ZtpW7ZtpacW2wr03PwyPP4O9q23APH65O28dIklnye7rsCOMJ6yrMbwKXP+f1uf0oPM1jzzb0BnCUfAK+JXsi947yrZi3iOY8CkG9E/ppH9Yj8HBwq0k5PeEdbuv9tbd+QTbanZHQCOErvvQdO1r8Lapd20Rr1r7ahnUxe9rfFDhae7Xj5cFk5I3YDpW7rLmq2HS9v9GuLfgDXfw9cXd647Om8By63VV1mTQFgJecStNE73mLZGPjZHAjg0uKr0hlhIV+gJw3lLhaVtXaIMvyJwvCkIi2+RhBlLdQri4z8acg9v/LA2/faJty2L3XbvP1ekPJjLvOf0UY8nz5TsMbrri5Jpn7Za1tLt8O2FXl7n0Ll7UjbeGkST3ZL990B3Lp7xoKnbgCX0uk4lw330xlB2D0BHHbfwOdCJSjkQg8AaEMLYW8RbbG3bFh4jQV5L3kHy8MKfB7V9ntwpF+ojEz7Khzu2/wUqEz/SPBLDODzoRIUCOAA2MGGXZ4mv+iXzZcIify6B/lE5dMg+Vj7P/7wjm3fyY8/dGwrdMu2Ved9RhzdD/fts34L9RCLLPgtVPD5UAkKBHAAnAu694vvjB1eZI9AAap3ifLVEbp9Ov1afGXdAXhNVAIAAAAAADg3dcI0qhMexHib3t5ub/PVvCH4OcQ25+tg5D2CZ9f/KMbbdZ5vb2T/hSnI+/6yj9OR/q9lL/LL8wAAAIAvRfowXG/TnBbJZcG8DurEO0EA91HUgdNwG0Lf7pM9BE4quKfgKgdW85LfrutIAKfLZPkBAACALw39UxbzsEgP771I7gsmtvOsejPPrp+4tw2vvJduMToB3HAbU9A2XGmXrB3462Csxx4ZAQAAgC/FJey+zWnx1Yv0e/CshfpZ9WaeXT9xbxteeS9dM05zOLfpG8GH2ucggAMAAAAeBv0TF0pafFsLcAtavOPl1+k2Xqdqoc73LgWmsSpH7Vb5K5Nqw4Vf/qUFf2kjtl0CgGGRiWSkvFb5UrbOL3LNZv3xvDHUIwOO1TZ0mfHK6x/FuXV9d9kmBVS6bN4ls22jdB+XvKUvtwVwegcuyzBP19tVBnCVXYXdRF5BtwEAAAB8QeKHeAmss0h7LIt8vv9pGFPgoHZahni/lBVAyUBoD0vbYfFnwcewyMIDrBB0pcBJ7RKtO0dDDMDofC5jqr+6B0vUH+QOwZu+D4x2na45LQdVa/3tAM5P24NXvtgmyxyCONV22pmVduMM8V44FRz3/GIo5w/BzjI482QHAAAAvjz8YLjNYSdKLqQt4iLL00Iw+C4BnBFwGfm83vo4BzGSKb3sc2P902TbKwVsVVoKCGMw9PEBHE8Plziz7kHObIdOAEf3wk3yHjjtF/oSava3Qt2GlhEAAAAAAX6wBFlDK9Cy0Av1ywVwnfK9/Pl6Deeoy48vHMDlHVmF6teM7F/tFzKAs3YnEcABAAAAm+AHFMClhdYNWiT9hXqt++EBXKpTteXXWx/3ypd8nVfXnwO9uh5tmxgYlR2+Sud8OfiDAji/f3o7cITsX6177RciHwEcAAAAsId4f1LcCVkW4TEumu3FuoaCknzpLN8Qr4MiucBbebLMBlLQw4OnYcgLvg4A5DG/hy6m0T1uLBCz7oGz6lf3t0WsXaZyzrDKHe4Rm2fjPrQ7bBPQNuDpIZhMfUd6ev1u+sQwLmWj34zGPZSke6y75Be/iHrlz/ESrGzDkx0AAAD48iz/jPQUZr5kRk9K7l0wh6rs/kuolxDc8CdJqS51jkcoWy75uU+JXowA7hKDp9L2HJ66rGSXT0t69atgMJKfxIz2qXfp1jx6elfWx9o/bBuvzpQ+UcCe6pYPYHDMAI6eUGXyr4HqSu0Xamc225VeHD2WIK/I6skOAAAAfHn4QbyEapy0i32XYAEAAAAAwE5Uwn7WS4rldRFqtwYAAAAAADwKlQAAAAAAAM6NSgAAAAAAAOdGJXxRRuPBi3vRr9KwSU+EPrz9jye/T85/EIF+xaF+51x8iEa+I+/5HLP/aMjO6mzqDgAAABxGJXxREMA9herFxRr1ZGp4TQv9vyOAM9uIP+9Vgiv9M2eSI/Yn+bXsrE4lFwAAAPAQjFc10IK48ylSVcenYkcwIcptC+A+EqP/H4n5gt6C3/ZWm/PXoPD04TaygC3uBLZfv7I/gOv3b0t3AAAA4A7S7g//HUsEcIKtwYSkv8B/PO8RwPm/reu3vc3m9ALg8C67XqBk/ayZ4DkBnK87AAAAcAc5gGPvbjMCOPqFhfVSVPUyWla+ovwQunwRbXkRrqzjwGI3lB2YSN5liS8ONoMA0i8t1vH3P4X+Kxt0CzLwF/3O6kW/669TJN15G1W9Ii8HN63yg3iZ7ricuy0I2aZbaVv2+53kX6VQZB+IAZzUvWqfdA/9uDWAq3fg6rqvdQAnXw7N/agrOwAAAPB0aPGjRZv9tFEVwOkdmvr3PCPynEL8uSiepu97OkqSTS7sCf6LEPSZfqqK0ql9LauWk7ejz49ltvxWqjzWddm/UhECrCqNl7fLkJ6WLXw8mXS61e/3ItsoaJtzv6lfFu0EcPln1ggKbtfgyrZdyyftS6GyfwEAAIB3Iwdwl7jrQIsUD+Cse5iMm8ZbC3G9S5F5TCBQ7RCNQ70AB9ljO3Sp7TrSAk2Lt7VTciSAS7tYjXL3BnD1uby8XdfDAriN/X4vZtsBbfO4Wxr7s/YfJ4Bbyb+1mnfgbJ3rAI5+2ot2+IrP6vpl/wIAAADvBgvgLmkRe3QA5wY4j2JIv2cqb1Qn3ShYyzrST4XV+vI6fDl1MFHq14GXzJfHui4EcDLdsnkdwMkvBAl3NzTaONdttcsDuNhW/I1WOla2YPXotgAAAICnUwc0YWGjQEhcnuKLnXUpTZ5TGJqXph7OEmSU3bW4aE9TCUin61X/WH06VwZQBR1M8Pr9oEEu8NqWVT0HAjhZpn6txRY8mXS61e/3ItsoSJvbNsrnUj06wOLoAE7WVfxU644ADgAAwMmoA7j1viG2uOXdiHCcb+AWi19cXK3AKL3MdOL3qdGOmfUghHVps8Ew3q7VjfV0qeytCjDyQwp58ZW6FVoBHOXZumV7VboNeeGXC7wODHIZKzjR59bl86sxss3y5WRTTpfctg5Cq10op9/vReuYoUvv5b61sCtsBlHxXBXALb4xrv1Al0PjAwk5f93NC/Wn/DWAK4F5Prbblv27j0M+DwAAAEREAOcEE/5TqAnxpGkVWITLm3VevQt2RwA3z9UTgfM8VefIIIfOtQOGVgB3UfJXclZPofJgVS7wjw3gYsCan5SkfhkOXEK9iL6rdXvaU6gJrWNm0ZVeD8Lk8l/EawRw/OlcYvGLfDk0sthc2K4EbJfaJouP5QDQ6g8tzzYO+TwAAAAQUQnghaGdJZkGAAAAgE+HSgCvAl3WFDuD/i4VAAAAAD4RKgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuVAAAAAAAAzo1KAAAAAAAA50YlAAAAAACAc6MSAAAAAADAuVEJAAAAAADg3KgEAAAAAABwblQCAAAAAAA4NyoBAAAAAACcG5XwRRlvb/P1Nqj0+xmu8+3t7e02XweVJxmnt6fJsY/xNm2UeSvn0W07ue9kOviaBB9+Yyz+LM85zuPH3Jk503zwlezuE/3vLH2ylWpMvpjsD0AlfFGeF8Bdxik41zQaeYLzTGqPX0zOo9sOUt+pdPDlyf4s04/z+DF3Zs40H3wlu/u8ZgDHeWXZDxF3GObbdagzwuCaRl0A7Ge43uanBXDPmvQfX+8+3UbVNi8fJhoDZeMUgNV1pYmKM8+GDJe171T6A7jPvo/vny1gvigggLuPffPBc/lKdj8nj/H9s/jTO3JJi1SelIfbddYL4XCNCyFN3tN1ZEaKhi/n7uyIpe1pjpepMtZiS2kkAy2mdE7VSaGOUn5PB1bbr2oBKm3ndmd1zn1wnebpervKSU3oRu3HPCMISYxV2dq2sv26/lnVn+1O+abuS/lcdylbaOrWpB/AyXxF8OvpNoYgjgcdto9agclhhlHZteR7fTetfSf7TY4JXbYu7/vNA6jmi4s7X8S+t+eLoo883oDQrfJbw+d53dZcYvr1BrwAjtdd6y7zO7ZJPrTHNi3d5ZjOMnIdqvRKPquf+Nxv1y3l43n75oMOYYzHukN/pi9eb/O2MaV0s2xvjCklRwt3nUrzAbNFHdwW2475dhxrPDfn4jifyn7P5+RyAaFXmFdG27aebsU2Pb/oz4VyTLfGw8P86XWIH9Zv0DQQhBFikJN2KHLniQ4qFVoDvcEyUK5jOXdwFls5Sa/yJXmmXMdSn3TAbQxGudJ2aC85sVys7oEcMss+jHlgJP0M3YI8RjBg2tuwbRWg5N2pdbAvg2w5n08awe7X6BdK9ySfK9tSxtWty/0BXNgtCvJIG8njSJigOnVuI34JKrZYbDroei0ZMrLf6jFB2DoENvnNffAdN9mneb4IOjjzRa8vWtQ+SzC/NXye24779L1j2grgKt0v6QsMs/tm24QAYi59uJGW7t5cOicdpOy1fFY/xTRVN7NtZdc032Sd9s0HHVLdQ5CZ9KN6o0xZhpZtKt0s2ztjSsnhYZSvxqPwBa/fQvl0btUXvbn4Ql/6dL/XtpfzVoTsGsoZtvV02+UX7DxzHhBjurZNzcP86XXIH8iAi2FmaRxt2HgZJUfI0pH1+btYnaGuTzpVxHG4Q53YCOCsCVaVP4Jukwcplm560dgh02LbYtdkO9dWPd217etvjTGf11nn97g3gKt3kmu7SV0iVtoxUv3Kn2o2t6fGBGHrQMh+IbTf3EuaL4bh0HxR8uVxj2GHD12U7fRcsrf9graprqutu5/PdzgPo/xGjmmOlo3I8tn5Mc2vm4/h3nxxJyEgm5LO2Xb21aSA4RdB1qp8RstOkPzbZLfLS93zA1PTKOc+bXtrrm3bdsvGhq6HWP3TsK1Xptim5xclTerooefCgrTpF6AckAMpA6pJ4CJuyueDuByrelxoW3j5FkxOQB2dkJOOXV9yDgXbft2MDqZ02/L4XrQjyyBF6xb143X4MmnbSrtqnb167WNLNjuwtyaVFs5lwpZtuC7Bb5kfJJ+1dYlYaUfJlwvoW6mnb6s92W/E1gDOtE2A+839mE/obpwvpB9Zetj0FiLt86Vty+Z72y+oAK6ney8/yzKJnfIdtHRv6mrJRqzjxirLx7id3+rnffNBhw0BXMs22e46eCO8uY7drtLEK6/XqWCTNxkYOrYTc227fr3WaOxgrB3AeW1n22jZbVms84pcsu+Un2ZZH+VPrwM7WDpIOa81sI1Jp5RpdYQmOqLett806WTnaU7oWzlpAKdkkvgyWbaVdvXrl/Xax73yPG3fhN23jcxX55J8gly3VV75+d0M6d4NupdIy2rJkJH9pmWzdcj1+v3yQNKErtP684X0I0sPm3YAZ/m8udPC6tNp23haAHe9Bh23jZOalu5NXdW5iU8UwLVsk+2ex44VQLX8rs328ncFcM369XyquSOAc9vWstuyWOdF5Jg2/TTxMH96HdjBYARwhmGtbf/1/DTgrY6wkHXLgWW1X0gO95BO+5gATrbJJ7VtunkyGelVANeznSwvj0t5Xbacz9P2Tdh6kG8P4GLbcpCT3/rfCtlE9WjCmNDf7C0ZIkJ3NSbiOV75dr8+ECuAM+Sy5os1f+d8EcZpQzfZtrSdypfy7EAFcEZdTd0b+fS/DiR69PxGt8/LWnnNS6jdXW0dwPH5bt980KEbwLVts8rO7h8rcvXmyh7byq++MMYAvuRJ28pAqzcXxzpk32pkvZHVPw3b9nWTssc0LYt1np2u58KCL8enhR2YAVyJgPM5ZEDpPGS0cKP6PId83RE2decPS1v5PoB8ju7AirwAsAE3jHsnPuIjArg0ONKAyE8YrfYwdKPzSL9SRx500nHlwIq2rRw/1V8mq4HdbC91lcelvJQtH5PfuLp10YN8cwBHclntrAGs1CVt0Xv17YVuus037Aa70/jRwaHdb7GM7Ld6TMR0t/wmv0kLlRFYbsYM4MQ3Zme+CD53YL4gap+NdWa/tXye2077jfSF7egAzt4t4PNK2zZMFpW3hZ7ftHWVstcysH671HO9X3c9htdxkOaE0I/GOC0PH2kZXboBXNs2leyW7b0xJeXwMMpX65QIKK1+y7aLD2CI+aAzF8u+sDkSwJW2bdv0/aJuW/qDXseU7gzLnz45KgEAAAD4IAZjgf/KWEEQAAGVAAAAAHwItAP3xXZROiCAAy4qAQAAAACnAAEccFEJAAAAAADg3KgEAAAAAABwblSCANu3e3joo/HvRuzj95U5tqnTPyev6RfnwLZdejJPpZ8LW3bQZoTNdvFea/RHjLk9un1Jv1EJgj0GBK85YSOAezav6RfnwLbdRywm+7FlB22+5EJ8B++1Rn/EmNuj25f0G5Ug2GNA8Pkm7PsCLd937qv31fh8fvF+vLLtXln2c2K9Q+yr8xnWaE8HLx0k0gd6ySm9MI8i7LeZvZSvGDC83JA+y5csLmVjuZRfGTsOuPzbkFZ5ejFhznubp/BSVZr0bNlEeXpzNssj2SvZeoS600tmDdm7ul/osff8IsPr7bp3wha61baPda+2eaOfZEp56cWVY7JdkCu9DDK8dNHJD/ZNdccXaxZq2dK3LYV+Ia1Nr3zMb/mFtA23i6VbqGd+0O99bvSL0veP8gv2gkwBDwZcv7hYQfOBSbBh+0fYpkfxCW273G5A1m3MB6p9Z8yVvKIb0dIv+lzdr7xvpOxdNtjWHjN9v5HpJi3bXGy/C3m9+cbIz+PVnI9kn3XnE5Kd/36y0e8u1kvcIyRTay6O51njK6bJ+kw22GaLX6xpaQzI8e6O5w5ynahtZYyHVL+sx6bXr7p+WXfbby5iTtjjFy/BpXqTckxcjLX+CHc2cHo3T3Ky6k3IAxvgoS7+dncaVIvRWOBRlU9t049+x/J5IU4TTlqYc37+qZMsJ387eE5jyvWht+avbWvZu7on+WP5IvvWwZHtzuXPto+O6bwZnfXZENLJMandMcrn5JM++i3W/uS/ayIy0BNbJg9Mxy8u+SdT6n7PA9TSLeh+h6wVzC8Izy9Ifkv2u/xiNH7MfB0H8dj1i4tlczHB9+C+k9LKfEDt3WmbHksZaz6obWe/Nd6aD8qvi8S6pW55zIXPQrc8J5Q2mH6pjpnLJuYzW/YGG+Yjd8xs8JsmHdt485Eqa803Rn4er1o2P6AiG9h+HP3B7fcOtZ0TTL+m7ub42jEXbbHNJr8Y4jw50y/uCN0pAHTm0u1YY64e79wvdfkWlg3t+n1/tvxGyrzPL14A+VMVEtnZnqETasKQv/dZl9cOQd905iCPNn6kfCtKdVUTzh0Ysrd11/Ltu2Sy83cdL8k29JMxYRDbP3FSJkydT/Jq5/+4AE4ec9ta/Z7tZenW1uM+3t0vnDGR/V7alP+mpra5lK9Fbz7Q7LNND92Htu20jYnefLBXt3qhJqR+HC2TLftGnPmonCNt2/ObFr1+l22V+qsdNvpszTdGfm7Tmo+kHlwOKQOXz5a9j+w3oqxDHd3NfNlXDXbZJp+j/YLaL3MhZ+uY6qH92x4PO3QXZaSNrfrt8wjLb1K9Kv3ToA1UIw0rj4nFcahjqZ4Edy7LsXOarksPHF5vJm8tl23b+K1jn0MS6XcwmfzWwNh2vHdgyOC2xvymkb6tWYP+cwVw/HIIJ+pk6dbWYy8f6RdyRyDWt7Yfvk2LMskvKF22bcnj05sPiHts00P6hWc7azHpzwdHdCNKfksfnWfL3iK2z9uWtm211/SbJp1+V0FDYqTd0vi/NSbfL4CLfe/1exdnVyvI1tPd6AfdVw022Ub7pfSLeTJ2YFk+96kIu0S7CWvM3al7sx47XR4XbL/Jc8Ihvzg/nYGrDCiP4yQlt5a5c1mdm9NkXYQK4FzZMkO41BLvEdh3D1y1NW7I3tZdHu+dsBHAyWNu25ZtLN3aeuxDXjJ5X7+odwTULsoHB3D32aaH9AvPdtZiUvL4fDCxtvfqlueEck5LH51ny+6T2w/HznzUaq/pN006/a5kSZwogCO8fu9T+1Nlu57uRj/ovmqwwTbb1qlrkF/39w5Zmlhj7k7dm/XY6fK40PKb4aBfnJ7UKe5Alwa0j9fzDeeyOjenWZNGnvT6shmM3rcQC6GLIbulqzzm8u+bsHEJVR6Xc9u2sXRr67EHKcveIOVev7iwHYFYV91nckx1LqGm4E6WsemNOanrXtv0kH7h2c5aTAxWO8bjvbodCeCO97uo25mP3POJpt+02N/vxHkuoQpEv2/CtV1Hdys/jTnVhkXXNtv8gvKz/1ljxe7XPVhjztBd+ekWrHrsdHlcaPlN4ohfnJv0YRBPuaxOIA0oj2PZUG6O3xDGsJjkc+SAk+WX86fcboyOyw5cLBO/VUW58nnxm9G4ONQcnHmVe+9TiEHvWNaSvas7OXWQP8q+b8LO7Re7h7bZALSefAp5xqB/TgAXyxf5djo/s29dXg5ybVur3/MN45Zulh4xsHnrD2wJl3vpn3f3CyItArq/Gn6Ryq154Uk2S74O7nyQ8+6xTY+B6eXZzlpMyL/1fDBKf3XGXMkruuU5Ybs+ud+j/LbsDXL7zlzaGzOBht90adnmYvtdaVOPyccHcBc1J4Sxn9aCVWar37fQsJ2reypnjTlZh8kW2zC/9Pxi9YOkg7zvS9qtevhmE9aYs3xwh+6caq2o1wlevzwuGH4jYoTDfnFeVMKHEyY92REAHCJOOvaAPze7F38ALvCbe4DtwIuhEt6XYfk2MZTFNb82wPoGBMBeaAcuvmJE552Z+KoAjAOwD/jNcWA78IKohPeFtozF1q56hw0AX4h42RfjAOwDfnMcrD3gRVEJAAAAAADg3KgEAAAAAABwblTCJyU+zbLvXij9BMw5iXK+5s23ryz7UQ4+pfUufLTPn9k2nOK3Ou8oW23/EWNmq2xHeXb9H8nZdZNvigAvhEpwuKeTz+/A9qLxHnK/Rxsfx2fW7Tiev52Bj/bHM9tmK0dteLTce/Bs2R5T/yPqeDyP0e153LO2gw9GJTjc08nnd2B70XgPud+jjY/jM+t2HM/fzsBH++OZbbOVozY8Wu49eLZsj6n/EXU8nsfo9jzuWdvBB3MJL7vjL9CrXwAYna88JZpJLx4M5fmLXqWjtn/TMpfnLxls/Rh1ofF+L3ocPF1eiD9BUqjP7elWBt76IkDj/XTxN/goX7xQVS1GciBvsE0DqVv17rz8csj0gskgN/VTeMlkLUt4UWk6p7K7fJmrZeuq76PvxDp6thXyK7vGSYW/PFPanh77r16eSf2w9ZKW8cJS3na2TW6/tG29zDKy/R1SsX6pGy8n2486lrql7LxvrLLSdnLMUd/xfpPllQ6svJS9PZ/0aNlGv6g5k20v0xWVbLV87nyy4M0n1ktNq/yAGM/ihaVyzLTmm48bM7ZfVPU3xxQ/p617PC/2k9cfmr7trRfx9sdqwtBtr2zSdnXb9TmhDT6XNOfivt8Qlt9n20vZrPLglJQFKU+Sw2A5ZiNKH0pnx3fpyLf1i8FZlc3vfWMDl5xogwNVL/xN9URHnI3y/uSf5fPS18UtTX78PUFxQq1/u7C0Leu17GCl7cUIKtjbuIcgV3wfGrXFf54lTGTsNy0rOegt1inP7NfURpmIFtsv51uBiJa5lFGyByi4pTfgl1+eqGy/vrMpy5dsv2kxulS6xfL8J9iKbXL7um1hi9WPjbYUsf7i88V38zlr+3lc0jlsQpeyc3mk7J7t6sAr95vWnc6v9BJjth6vW+cTj45tqn5K7LB9LRtR5PPmEzrW/un5LdEY08z2a/vrmOnPN+22nzlm9HyRbbSe0xxTpX0ekEvds80oWDnySg/X7hd6VUj8dYtwrObqDoZu67zfxbGdsQ7kMS/He3su3uA3lCb9ntm+6TfgzKSBU3WuRSOA45iTqT+hWRPR1m/T/AeHwwtb6RvKUheV123dEcCt8kk95HF+F1O9yyXrswaulncPxoQeBnn98yz1T2npdps7SKpfU5udfpJtaAzZA/LH7Gt5rTLyJ9h2sehXdJP9LvXQMh/54XCeJm0v228i+kaX5bYr/WbLqnWvx77WvZZ963zi0bON/rmcPbZvyebNJ5SnfVjboaDHVlXGlVXavlOPavuZY8aWhfrG1uUixtQ23UP9SzkVpG/EkjGi1696rt6JDF6b2LarbSH7voGai2VZ2V60vW33eH7Lb8CpIUfOW6f5MoqFHgCFQbyMd3sAFxzPZMNvmgZHjgOQfk/1St8ol0FBv32mJ4DjAVyRWxyrgXRh33KtemV9XtpejAn9aABXTWh0eXWq+tafNGxkGxpD9lR/y05WvdsXo9huTzdevzyud+Hi+du/sUq/0LZX7Qmk7Fx+XZbr0+s3rXvdF6m8wrpU1ZpPPPq2KXYv52+1PZeNdkMq+Zz5ZCAfdeYT246WDUu6XcYqJ497bT9zzNiyUN88Zr5I9U/UP1t3tjSWjIEqmExUc3UPrRuhz7OwbVfPtfY5Bd2+tK3vN3pM1bT9Bpya/IG2VOl+pvgD0vpE2ckFGsRya3pXAOcO6h5UL03m9D8NBprY5vRZnosAbm8Aly8Ph75Vusbyvb6TbWgM2VP9LTtZ9W5fjIRulGbswPH65TGXe88OEK+fp0nb6/ZqpOxyB863Xa/ftO51X/TKZ3rziUffNtxf9tueiLLFe4q4fNS2nk/o2JtPbDtYNizpdhmrnDzutf3MMWPLwgO4LWNKyyzrj7d57OvPgiVj4M4AztLt7h24HQHclrnY9xs9pmrafgPODF1bz9e+L3qyZCcug8+aKPn27BC+uepBkScco7y6LyKeP4zeQK+J8pb2woRkThKtAI7rwJGOLI/LwArHaWCV9ku94X6TZTGg/HpgNGyzGWNC3xjAhXPS7kLdb6nOtDia/Zr6ruq3oR70fd0M2QPtSSVe/ig7MevOyqbFqNYt+60/IXoLg6xnK7H+bHfrNxjt9jKDkp2X12WFPqk9sjnvO/PclFYdqzEbx2v4vHk+8ejbZrV76u89tueyRdvV8pnzyZs1b3h+y/MMX2S2z+eWMSNtL49l/bLtZ44ZPV/kvon5cizIMXUx/M7XvZ5Ht9Oab6wAbFsbtm62X1jYtqt92utrojcXy7Ly+BJtL9dYZvuW3/A07j/gDNCEmwILcoqZnkxyOkg+xbJ25JCeRKRvq2N8qjHUxR2AvgE55eO34TqPLl3I9i3kpBQGZmMQ6PRSTssmHVkeZxnSxBS+zYv7a/KkFZ7+tMu3bLMNY0LfGMCFb7ypbXXTMJOr1a9Fbr6o6zoiUjdD9kBvUimTaLT7sGM34VLLlfw2yB/ql21ZQVFCTcRbiPXzp/Gk7d32cr6QnfeNLqv1ifpn+0Vivxnnqr6QYzaO1zWA2zif2PRtEzADuz5cNks+cz55s+YNz29LOa5D5fPC9vxpwC3zjd+27CdZ/p4xk/plCdTdvmmOKX7OBt3ZlwQtS4PGfHP/U6i1buHpfdU3FrbtrHPc+ppzsSwrjyNyvHPbt/2mpClfBh+NSgBfAmuQvjZh92TvhH8n1ObmRQA8jNDXO3ffgOYjxgwA4GGoBPAlePEAbli+hQ5F9vxKhL07MvdQX0IC74V9WRV0OcGYAQA8FJUAvgSvHsDRPYX1pRLzUtsTyPdFvWebIJIvccLuB/jAMQMAeAoqAQAAAAAAnBuVAAAAAAAAzo1KAAAAAAAA50YlAAAAAACAc6MSAAAAAADAuVEJAAAAAADg3KgEAAAAAABwblQCAAAAAAA4NyoBAAAAAACcG5UAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KsHlOs+3t7e3lek6qHMAAD3G27SMH51+BqJsM8Z2h2int/lq5L06RbdB5QEAToRKcKkH9HAbBn0OAKAHArjXBwEcAODDSYNVoCfw0UgDkXts87kXzM+s23G+QgD3FXT8isB2zwO2BbspB8N1vo36hMQ9Qcpn5x7bfO5B+5l1O85XCG6+go5fEdjuecC2YDflwAzghuttftM7dG9v8+3avYQ63K6zPYmPU7n8MFwn1sZ8m65j2rq3HHrrwhDbNgfDOJXLA4t+E7u3z2qL0rJ88zSq/NouxKTtaDIaZevyvm02EvQrdZP8pXzRj9oJ58jLJqx8XTbntW2X8wq1bXzZOoi2Q3mrr01qvbN91Xmm7hv9qklsn7ctdbfk43W3dLfK1n57UX5BviXHXNM2Ltv6ffW3Az5tyVfZveHztmxRvlLWt22Yt3g5Yz7gsim7b2GRobQxK99w54PF/8aRtZvn7jnaPvSBk0/lt+hW5SfWfh1G5VNKN5M4pur2InmdyDr6fiPXBWvt6GCMidJ/um/pHD0flvJV3xt+Vdr2bCvWEXM+upePXKMvcc40/DL7bDjHXWe2+80nphyYAdzKwV2mpWNUoJcmjmnMk8YSDI6p7jyphE65zzlC3blzU730mfQs6ePa9hCciQemeWClxS05Gcldt3XQNqms1jHSto2sxyDoUw/2YalLTnrrREX1i4Uw6jvEyVm23bRdxNMt1x/qTnWp+luwtgmvfRumd56IlvJVv3LdL2nhT7Ipv0r6VX7VJLZfdI9tySAs90uQT/RNS3dLt8pvDb8I97Qy2WR57fM9/HGa/Toc7/XpS8c2ot9sv/LHnOdX6jxz8dC2s+eLBqlvqn5hY5Zs584H1M9kk5BO9iGbZF+jAC71uZFfy2HplvFsV8pw2XV5B2v8rn0Zj9t+I/Xw5HTwxsTqC/VcmX3NnCvDsZDH8Cs9VzVk7s3F92DJwmzfXocsmWVfNOB2Z36ZfTa2V9uu8pMNfvPJKQdPCeCWQSAdLSx0acLVnZ/ywzfi+5yDt0Of5zkOfnJI2WZAdbwcKJY8MV2nbcWrs2cbWY8kTajNbyFSP6M8y2t+q1G2i1g68Pp5WrP+Hk77NpbevA/buku/yue5fqXQPix11/I1ELrrstzHen7Rs81WtI48ndeXfdqfe2q0fAXZb4S0rSWDS7KtSjd8xLLd5nZ4nWnXQ6NtWtluTP+nhTAuarHOGMD5+aYcpo0926V0WohVmS3oNvk4s9qt/UbaRp/foj0mSn22TbTsBPmdW99AX15luiezrl/79D183Bq97sDRZ+aX2WfV+Rf5pUjbpvabT085eE4AV0+q0rjmopui8rudI5xLDkH/k5MM7HM8p/p2oYIA2b48LufptK14dfZsI+uRtCac+hyr7S3lrW/EUt5e/Tp9G963Qtm+jaU378Oe7rVf0et1pF+10bpHfUp5LV9NS3ddluu7RTddviWLjdYxYPVT8ultfWfpV+f5umUsHSOeX8nzrIXDqlcet+n0jSULt92HBnCl7DDmS17WzmWL0q5cJ/p+I/2tJ2dN0+7d+jr9drH9Svu710a//nv5sDV6QwAnbaflafjN56ccPCuAK9ucsWO58XXnd6L7zQEMkSavaVqdc7pe2aUoUb+aJGT78ricp9O24tXZs42sR1K+zfvO7LfdL9+zXaRXv113H1Wv076NpbexA+fqXvsVTTC1X/WQE5xeMLV8dfmW7ros17enW882W5E61um8viM7cJ48bd0yWgY33QqaArrPrPLyuE3pG51X6udp59mBM7AuzfVIawW1UY9l3W5zBy6tE5vkvGzxG91+4cCY2hXA9ep/AB+1RncDOF2/Oc+7fvPpKQdPC+CyA75pJ5TRdZ4w4+RRJhIqQ9/s6DKoPaHaxPpLpwYZ1ompHhjjRE55JICjLeijgyvrqMu3bSPrMUgDKduP0oaBy+7pU5cvN+MOSx/kuvhiMxi2i3i65fr1PSfbLsHUE5rfvo2lt/Bvpntug8vG/SpOZjv6JbU/psUt3mfVnzQLQ1N3XVboa/gF1WOem9J8WTyif1h9ae3cbredpR9D9Rsh/cobc3KhLLZV7ax1PDKAu6zyV7KzMUu2c+eDdwngHNvRfUr5nsl0Hsnqrycesg8Kbb8p/sbXic22d8ZEsb3uW6u88rv0v+VXeq4qtm3Vv9ZtzJVZB1W+S2qbyr/nGt0N4LTtSEbXdobffHKiY4aOY2hHPTKJM4xFKuM/4RLLrXnhyZQor6zDIy6uebKK0XulB30TSo5LDjqmxTieIwetPC7Ip5d2ffNkMsjyTdtsIdSdAgySvZpgfH0y8XJIaV8+5BDy6BKisp04x9CNkHmbd7F4vaJ9da7C0lv7d0v3yq/ShCbL+8T2ed3rzc8JLV+NpzuV0WUNfYVfEFE341zDNpsY6qcpeb/7TxP20fLV1P2m+y5g+KVKZ7bV7VlBjradPN5EZTc5ZjtPoabyMkB7XAAXy3PbxTGwBHBp4V7lTk+37mb0H5pp+k0Owtg6scv2xpgoAVO/Psvv1FwZ5It+FeqX9VW2FWOmMR9lQp7Xbz0+Yo3uBnAxndvOXGdSXZbsnxyV8BRCFG84HAAAAJChtQLrxDEo8FGBzUZefY3+on6jEh6OdYkIAAAA4OS1QqaDbcRXw+j0Hq++Rn9hv1EJDyVfapKXiAAAAABivY8Ua8W788prNPxGJwAAAAAAgHOjEl77WvhAP0+1/ZUEr0x+EnLlVH0Wb2TNT1ru5+CN8+/OeDK7vyexj/fp3r8Z/B6eWfdjeYbfvMqYeR9eeh3bSbUWfBGdQUAlvK7jp6dhXk7uB3DOPqMnrazH5bfwKovRMxbiVwEB3HGe4TevMmbeh3POic/lK+r8xVEJr+kE6VUOx4KF1+d4nz13QY2Pie98rUoAi9Fr471K4BH+5tfhpb8WR33/aLnPyfE5URL9rbrakdDnfiyP0xm8CCrhJZ0gyHz0/TefgON95i+Gj+JY32Axem0QwB3nqO8fLfc5OT4nSnx/OxuP0xm8CPFDflEfPYZ8NZyg+QLFDvLlhuXliHXbR+v3d9/KwCv66UCitM/bji+zNAct7SrtGCQt3aR84bwddWfMgWu8mLKU8b5VivsH2UsU5QtFcx1d2Q/twsXFiNfNfxXBCwjJDqp9hTUhi8WPflKG+a30m2DvrLOSpdTPZZdyVC+/pPFl2e4oxotqLRlqtvl8pfubDNJ6frXNNj50j6usu9RvjSdVv7CN9usGwi/IrjHvgO2kXF3bRWT7RX57zCh5WnT8xpqrQ15+IWu6jSWUoRcShxe72vmhnpy/ts1eOi7G5xa/KXn2OnYMa77Q+bKtai5qzcVd25T215fYOj5rrgOJts9n39s7T4MP5sLewDzEn8IQzhgnHe8nTHrExbY4y6B+GiY4jfkzHbIuBzdAKE45p8CJ6uaBXtW+aJvvHIWBlQZweHR5o3xUR0u3Vb5sIzrHGYAtzIFLb0dnj1bTu3I8G5mT0xoYk22SLSu9U9mu7PE8HWC3oIWaPRqeZMlymv2dztF1SSydeQBX/zwMpdU/Qcaxgsnid6F8mpgr/Ud6a3jyJ2PM3UUaz/UkTWPb06FQ7ZYym9s+b73FPxNt4KU3bdPF6r+IHO+qfu7T4djyaw/tF5SW8y3b0WfPdjot09hJI32Mfo3Hccy4uvfo+I03V6uyIZ3mtGsZ90b+IOcFNl/F93rxMb7Bb542pnx/W5Fze5K/5Dfm4q5tiu5xLq7nQo65DiT52j5f2lDzKjgz2jkrJ1gnPFYoOdzWiSE4dnI+6Viqbla/rMfD/zFsrVt13NMt5Md6r+E33sgmNIlvdHIroBC2k/IdxR649I1tmejYNy9la8NGPD2XK3A7e4u0xGujhV7E4gLCv9HrCV7rZ2HJU7dX7co2Ax9rIZb128e8TPBh1X8+ul9K/Xpy3gHzefq9xuz3ts8fD+CkLWRft/HL6PT6XNuno1/JuiykX1T9ZdjOny8sv8lo38/ptk29cr6dNGm8ezJZcyURgqb4/zo2UxBS/SSSkZ/9p9TZmq+kLvYxl82eE4+QbCMxbBXnKKvdhm5d20hdxVwo21dtO/Ib5cHL4TjHAwO4+C0ubyHTtntpS9XN6tf1OKjFPKN1q467ulF5qndcHD1PxJS20fE/OICzvjErWxs24unWJCXP0emSeJ5uu4VcjOSkVf9e474AyNJZt8f9lvusPEfbSNZvH/My++Rv0++3FsXno59Hv7d9/kUDuMO2ydTzWUk3bOfOF5bflHos3XybeuV8O2niua5M1lxJPDCAq+Yr1Z7UxT7msllz4jFkWz5eANeci7u20e0fCeCkrOBToAdu7QTaefwdrw2IYEvWzetXZT3UYM9o2a1B7+uWBtEUZSG7TNe4I7FtUtADR9pOtn8UPXC1bvsCuBQgNXXV+pm4AXYLuRjVAVtdb5RD6+Zh6LzUpW1Q8OW3FmJZv33My+j+O06/31oUn896kWy2z79eAHefbQxGfluCtp0/X1h+k5G+X9ev6/LK+XbS9Ma7XRfNZ2EuM4KQfQGcqF/N6bJ9+5jL9rgxJduyWef2fPl27V+j/F0BnDEXJmyde34DXhgWzS8DLt8kyZ0gf3sIBdLAspzHZKjvp5DfHKxvJrvq5/WoMtLx9QRftW+0HfPjxLD+bIdqx4fKt3ST8hxFD1w5IZPtrXey5cngqurMu4XlZuHhNoy8P/WkaWH3TY/0Qua0ONq/1ZdkF/7ap0yAVCbcLzPTvUO5n8bbNd9HlM7nPivr0rpJv5PH0Zfywr9eltulQ4Nkq6xfTB8a9/HVZJ/Ptrbv4Yp1+gGct2hIW8jjLRSflfXrukT9zKcr24yWfgLDL8hW3C+k7XI/qLpMv+F5WrcAyS9lX/v1ngAu1d3wG2+uLmXvCeDq+YrmKm5HrYs8jvLF+aLc7F+PqVgm6GB+GfPQbSlEwJnXipjfmYu7tslyx/nQngsjeh0obVg+f79twAdD/yzOkgfMNQVZwgkOP4U6pCdqEjM9WSMcxHqyaXP9azt5ALUnMHlM2E+h5jx2mSS1Icv3aOlmyXMEq8/Ct7w1wIkTb+gD2R4/TwzgeKmo5NW7CRsCuDDZHJkUlrqXCYa3bd6L1pjMmtCElvslPO3FFj9aqCmgW/ut9YsS1kIs/U4ep3KrTwwPvYQaCH2aFrGE9dSeRfb5tc/I76XPBFoBXCxX2s/1SVvI441UPlvq13Xp+mufjmXJr1UbEsMvaD7j50jb+fOF5TcFKR8fP1a/Rr+5M4AjOn5jzdUhzwhC9gVwue1YN81V6xOXQX6pizwm6jGl58SjQUoup/FlSV/e2Rhy5+KubXL9uQ5nLkxtevOI9ClrLt9vG/DBqITXJS3KlvOCj4AmKWvX73G0JqxX4tguJQDg82MHiABcjITXZvg6v4V6buKk4+9c3U/rUsLpGeodIX75BQAACgjggItKAAAAAAAA50YlAAAAAACAc6MSAAAAAADAuVEJAAAAAADg3KgEAAAAAABwblQCAAAAAAA4NyoBAAAAAACcG5UAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJTyJ8Ta9vd3e5uttUHlnYHyCbFFnnQ76jLf5OhjpZyD263nlAwAA8AVQCU8CARzYAwI4AAAAoIFK+ADOviAeDSYQwB3nqM3fg7P7KwAAgC+ASvgAzr4gHg0mEMAd56jN34Oz+ysAAIAvgErYzzjdpjEuZsN4vc3mpdLhdp2X9GnU5Q8viKXO0lapY5xYe0OUiz4P19mQYzDSMo1gYtH9bamXtz8stojHWa8k33IuyTCNRj1HSG3PQv9jl4GHRbb5NmVZk+xvSxrJb8rObHoZ0vnJhqvt0znZfrbtLcbQdvYrWU8lX9afzln8LstzzWWp3WCrWZdlfVPppmyr+7VpmyZ9v7Bkvw4pn84nuYJNSH8aa7HOUEeyVbEd75vhNl6pPd7XAAAAXhCVsJMYRPG0sEi/SwCXylUBTIHLQZ/nOS7gFFzoto4EcEmnHDQo5A7cUT0tStuW7tvJC/oShOYAIVAHZFp23Z8haGP2Dp+T3Xlgt01/bXNev5avAw82zbK8vZ5tZXlpmx47/WINyNLxEsCNa3oO7KLMdI7sFyLbrqQt/T7NMUhGIAcAAK+IStiJXIzeM4CjtmLwERaidYckERa4uNjRYnUdSSaSg+1mrBwJ4ORCLpG22adnsGPQrSaW77Xdg3aUku3mxUbKHlJW+1jK9pbsvdo+2Z12xqTtLf14/dJOIQjJ9St5JCkwJZ9j9du6yPZ6tpXl5XFft55fWLJvDeDsfom2U7rQTmUK5BDEAQDAS6ESdiIXo/cN4CIUjFxvE+30rJfJcr20wNH/tOgN7LOuw5Yt1mPLtm2hl8d2XXvptd3jQQGc2360/Wr3ELh5trfQNt8TwMVzKXhM+cYO3DMDuDZ9v7Bk3xXAubILEMABAMCrohJ2Ihcjeakr88wAjrEsbmV3LS1q07S2O13zbpAseySA+/yXUP0gpad73d/kE77tLaTNpf9IeeqyKm9XANezrSwvj3v0/ELovjOAa8uewSVUAAB4cVTCbmjHrVwWy7s6cgGRC7CVJ8t0oN2DavGhRemt2uGJOzFl8QuXkhwZ7PSc58iWbnbnMgxDvbCX8+VCfSepbZKbt6/O28QQggH5EEMzSLF0H4ssIWhLdl8vKbo2ltBDDGVnMN7Iz2/0N+RZkQFYDla2BnAXw7a6X5u2adLzi8GUfWsApx/AiPnUN6E+PMQAAACfAZVwgCEudmFRGA5cQr2ExWii/FBPrEudI6EAbp5jwJiY5/o+nxg4lACTzrUX2lYAd1GyVffQLbKXPL5w9hbqBxDsVt9vdXxRjov7NQQKUlZ5HKFL16VtemCh9DsP7PMukizvs7S3BBzF7uyJ1Jzfqo/7E12+HUk3emqUzrfKyh2/XEexrezXnm18+n5hyR5koHN6Adwl9ov02fCELt2PWAV2AAAAXhSVsJ+hLDz5NSL8lQgAAAAAAOChqIT9VDtQcqcEAAAAAAA8GJUAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuVAAAAAAAAzo1KOD3j9HYbjPTHM96mt7fbfB2MvBo6722+vpNcr0S04XltU+TTeR7b/QIAAAB4Eirh9CCAeyUQwAEAAABPIC5G05gShuttfptv10GdeBoeH8BFG3jpWKhbjJ/YPl7/e+kAAADAOzFcZ7U7QgHS2zSyE+OCNVynJbhb8nbtqMgFvl788mde91y1fRF519tVBHCVXEvwuU2uIkssx5luI8sn+TzZgq1yOZEXGEZW76zK95C6Tdcx6VdkG5c+9OSjgHyai4y1bUod1E44h/drKDuvZa1+zHmFbLsNtlmwdYv19/zC4zpLWQtZv0o2JV9PN203Wzbq+3N/GQIAAPCi0GInF9cQ1LGFeF2wprTA0i7dAwO4ENjkxXuMC/a6IzjGBXIa4/nDSDuEJRCJC/GySKZ8kk3q06e9A7cGhVI2hmXHy2UI6cVOy4I/2IGFhaVbCGZCO0W2bJucv9aRjkv+6AQqKbCU/bqcn9seQj9YwYjsX0m0gbZN1M/WLdbb9IsG1ReQVG+WUcvhyyd9VaZn+XzZEMABAAB4EuYCpRZrL8DZglzgjQDOCCpivr24lkuo9gJbB59b8PRLCzULKqz2CEvOfP62QFdjtZWDa0+WYhvbdm9V4C31a7AGgzJP9q/ElsOyef3FwQ42222xepKe9HmmXcRUly7vyddqU9rNOw8AAAB4EubC884BnJ9vL4xrkOIEFXHHTsrRwtNPti+PC14QEC+xxV2yvYGcpVvekfRkIdvwy3x0bo2xs2roE6HLs9MSAJXySh7VvxInQJK7hcS622rV25NV1h31HCfawcw7i4OxG+bI12xTpstjAAAA4MlYi5d3CVUV3kR7IdYL3+cK4Ai67BvvJaP7vHRZD0u33QGcI1PEroPXtV7CdWyt+1fiBEjPDODCufQFhP4nPyYZ4rHemXXka7Yp0+UxAAAA8GT2PMSgCm9CLMRpkd4TwMnF9b0voW5ZqP0ggKF2NttYbbUvocZghH+WfVtj1eHkPTqAM2wuL6H6fiHbkMQ2p2la2yWfma6WLTz5Wm3KdHkMAAAAPJ1LvFl9ohvZ6XLZsoCqAEMvtnsIN6cTVLdY7PTCJxfDIcgWyqcdrBLAReSTmnqR3gA9/MDqiEGWlEUeF8wggOzKn+I0bdtG6qafQuVPmbIHGnL5sPuX80kGfQ+cpU9gKGVpF46edg11iPN5/TpAbQVI/adQy7kdWQUxGGSyWDt+gbZ83Ab7/QIPMQAAAHgaKgG8BF7QAAAAAIAvgEoALwECOAAAAOALoxLAS4AADgAAAPjCqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuVAAAAAAAAzo1KAAAAAAAA50YlAAAAAACAc6MSAAAAAADAuVEJAAAAAADg3KgEAAAAAABwblTCkxhv09vb7W2+3gaVdwbGJ8gWddbpAAAAAAB3oRI+gBjozNfByDsD40HZEMABAAAA4CmohA8AARwAAAAAwA5UwiFmujwaLpFOt/E6VZcjQ3pmGqty4bKqyaTaMBmWIGnm5eaUN9yusxMUjkW+cfJlWy/7KhYdKxmuLG++zUs9UfdYfljske1DeUoeAAAAAIB9qIT9LAHRNMZAaRivMVhR95PFgEoHScTRHbhSZ2mr1BGCs9zeEOWiz8N1NuQYjLRMYweOgkEK0lg9w2ILHsDN1yTfGAO5aTTqAQAAAADYjkrYSQyieFoIkN4lgEvlqgCuwOWgz/Mcd+cosNNtHQngkk5LGzovlqsvoR7VEwAAAACgQiXsRAYp7xnAUVv58uQcdgGrNsOuW7zcOU7z7TqSTCTH8nmQdR0J4NIl1ka5ewK4YMegW83W8gAAAAD4tKiEncggJV26fKcATjFOLDiLbU7TtLY7XZegTskWz7VlI7wADjtwAAAAAPgQVMJuaKcoB03rjpgKkloBXM6TZToM4+2a7y9L9VDwyB8wyA8p5PvOwi6WI4OdnvMc2ax74IYcoCGAAwAAAMBTUAkHGNLlvfk2LcHJ/kuol3C5036atAEFcPNcnoCl4Giun16NlyFLgEnn2gFUK4C7KNmqS7DVU6j8njwEcAAAAAB4CirhbqqnPwEAAAAAwKNRCftZLxmW14jgVRkAAAAAAE9DJexHvMg2vxMOAAAAAAA8BZUAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuV8KKMt+s8397e3gLTddiZf4TxNi11zd264nlv8/U2qLz35ZgM48Fy9zBusOurcx6/eA7jOt6sMffaupe+03ke/flinIq9zmCbIM8uHYkjtnk8WfaPtuGWft/LR+t2zC+eTXu+8TjbmNuJSnhJaocebsNg58djnX+MrQPzPAv1MRkQwD2H8/jFM6AxV/TSY+61dT8SpGydL+R89nEcW6iP2ObxnMWGe/p9Kx+t2zG/eC69+abHR9v0ENeZRZ+Sl1GmN0B6+T28YOLeet+fV+rT89s19r9OL/nn1+FZ9GzzFdk+X5xlMTnjQr2V/Tbc3j/7eHy9tW66/v2672O/X2gZH8v9882zbfYk2MFwvV13Rq3noOccvfwe3kJ8b73vz+s4qGfzM9GbNF5Bh2fRs81XZPt8cZbFZP9CfR7223B7/+zj8fUigJPcP98822ZPgh2YAZw0vDyOaXQ8XKfb/CZ373TePI1SiCZVvW/zbbqm8ou8JZ0zRz16+UZbNVFXXX66jSyf9PN0C06Ryxl6T9UO6KzKN1n0m9h9faF9MUBqu19Lv4xTaK+2w3CjHdlpjMc92bMMpf0oPx8AXD+Z18b2m1h+cOUhmTe1MYzK9vocsq9sm9jmF35+z7a27vycYeRjbal3OXfX5MN0i8xVWTnmpO5cvkq2DWOurXvkqG7apwnm190xo/Wjc3LbleyW/KL+Vt0h3xkTrcXk8Jjq6q7ni2teqM35ghjs+cKyzSpDPkfPF/6Y24Yl+1qH8Hlevz1eiYmVbdtO1l/Gje1TUvae7mW8Sd30mmz5j6d7zGvr5vqFkFHTnwtl/XIuarJhvpF9J3XLWDYjZJ/KuVj2u7Ttk2EHw/EArhqMZFTmXCHvmvLSwpMHfY84KSydMab2Uoe1ZZT08nt4OynZOZPDubrFBURPaDEQKZ29DPDBasdhCUJWu1ziok6yrPnhmOSJ5wwjC+AsmwTb1gMr4gRMqf5K/qWt9Zgce+23ZCurHpPoN6V87PcsbzVAWXvaNyxKf3DZrbpy+7bsUSddf8m3/Sbj+UV/zMh+DZOYMfmYpH6rJ5rSb9aYKzIWn8/ySdn4eapthq37Jch3VDfl0wT3a2fMFF9i+rH5TLft9J2o36s76Cd8muMtJneNqZ7uxnyRbW/OF6HOqzlfmLZRfqfni3XM7dUt1W/Jnuvn49mu39ExnW/Zjrftjyk9ZqKsvP7OfMP6Ruum5Vb+0/EbS7dtfsF0aKJlzLTnm6005hvWd0o3hrJZoLNGi36zbPtk2MFwPICzOsbOs8o7rMYR6dL5u3X28ntIHUp63zaEM6Fd8jfGOKGrybrLEHYn5uobQnZiWxY5qLl9J8ex7QCu56h50pJYAaKFtnkc6Km8GoixPeUrDuUbn2X7rbI3Jo2UL3Wo8fxClpN9KfNJn9mYfCw6/eaMOdI/pklZnKCpaxsvgNPltut2MeSn+rif2GOmPt/SR+L1na6/VXfl0wx7Mdnqlx5atiKflo3LEY4d21rtaNt0/O5u3bTf1Dasn1C067dtELFtx8v1dJNjWq4bvmy6vNTNLN/L51cEDN3KuiBlF36xCa1DQPlUhLe/Dd3/hdh3lm4ce8y112jbrtG2sv4nwQ4QwDlIHUp63zaENaGVPPpGE7d46fKwLOtjfXMhe8V8WxbpoKGOJJctH3E8gNPpW9E2rxe72qa7FvmV2va87bZu9Xk6veRLHWo8v5DlZF/K/D36d3RzxhxNSt5CL495O6p+hqe7LLddtwj36VCWteGNmVaQZWP3nay/V/eRAE7Lsg0pW627lm0twxbqlm0Llm06ftfN76FtI4Ocft22Dda6DNvxcn79Vr1GALejvNRtS76ut2Dp9lkCuNx34dhpbz1PjTnCX6Pb/fYusIMtAVzeKnadUSLznI40sc+licPaCZHnbc/vIXUo6XW98jhjTWgGalephdHWhklFOWhokxaQodGuFcAlndxBHPP1YNiKtLlhw9VeUVdrUG5mqYvv0mTd2vL7k0bO177AMXQyy8m+1ouRP/lIerrJtiLRR+x8eczr0fUXPN1lue26JbhPz/V4UrKqCV3rZ2P1nS7brtuqI2LrfN+YkrJZAZyURS3UDdsWLL16ftfL79Hzm2FD3bJ/GunVXNuT3ShfjfFt5bk9rQCN1y91b/uNmG+MAK7rF120jK30Mt9sRfc/T1/rV+O9YI85gVij2/32LrADM4ArgzFc+14GLRnAd0aJzLM7zKP9zWdrnb38HhTAWJ0k65XHpbye0BaG+tp61HWr48pBT+XjjZr5nLW+0Ke0jWztZMR65mky9CvnKNmJFMxzHar7A5Z8dU/IuPUGT7rkkWXP9y7IgZdsQBOM0qsB3ROR70VJ9ZCtKrvnLyqr/JbsvYnR85u6vLZtf8zwSWS9HLzVBkm3MKbX9FK3NeaKjFoWeczPU20zbN3jF7TDugWKT8ty3pjxgywPq+/0mLTqzn5t+3TEXUzuGFNSNqm7OV8k25d6fNvKc1TfKr/T8wXll5vELd3i/aF6nYryW7Ln8rlu33ZZbqmX7lc512rd4nlZZu1TYox35hveN1o3Xb/yn6bf8OD2qF/08Gzbm2+24s03pe8s3TjKZkRvjVb9Fs8j28r6nwQ7MAO4S+z80GEkuHYW5YwVMs8q30Y+obI+hbq5zl5+H/kkSrSTrFceZ5wJbXGOotdSjuxr2d9jYE+/0LfhMQ6u0v7SbnLYaDf7W2i4FPJmOX/GCeCSDMUu0pG13crDLT0WWy6DgD+xtt4oymksgi4UwKUvIqvcs75nIW6bd2Sv9NcLi9S/znf8YsOYyRNR7te9lxmj7+Q6IrysHHMlT8sij/l5ql2GrTsRA5/Dul2KTyu/cMYMHcdztH42Tt+J+nPdsb5Yd/Frx6cvzmKSkD5l+qVFV3c9X2Q5eD2ubVcc26wyFL+T80V/zPkBnPQbacO6bqd+bqN0jko359p8jjWmLJ+SY1zKJ2UrfaN10/VL3QmpF6/f0o2OY53b/KJLZdu6D/35ZiuN+Sa3a+pWzrNstmWN9vxKyfEcVAIAL4M56L4gwQ7WgvkJ+My6AQDAHagEAF6C1iWoz844lG+P+bH+T2OHz6wbAAA8DpUAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAAOdGJQAAAAAAgHOjEgAAAAAAwLlRCQAAAAAA4NyoBAAAAAAAcG5UAgAAAAAAODcqAQAAAAAAnBuVAAAAAAAAzo1KOCnjbXp7u73N19ug8kCb8Xad59sb2W9hug4hjew5h8/y/OcwTkf6r5a9yC/PAwAAAL4UKuGkIIA7Sh04DbdhoP/3BXAhcBplOgVXObCal/x2XUcCOF0myw8AAAB8afRCXi+aKXASqMV8nEK6DgjGuuzcX+gBR/fPPrzyXrpF7EPV50swNaa+HK60Szbfro3gSgdjPfbICAAAAHwp9CJpBXC9RTSUCQGaXKDHquywBHoznTeNqg5gsc3+Pl55L10zTnM4VwdwjOEa+rV1DgI4AAAA4GHoRfJIABcDMuvcOoALpMVepTcZ4uW6KvArafwSmy7rkXcX50WWMewiyiAkBqZzPE5yZxlCXvrM9Qm7URsD1CvbjaTgVu9iWTbdg1e+6J53RHWf0DlRnmYAN8RLqbPUedEn1z2MyXY8gBvK+Y/UnfeL9LWt/QIAAACcHL1I7g/ghnVx17ssRgC3qU6JFcCleqoAbg8piFnrlHLJ43ypcLqN+XPSdaYb7Vlgt0+3hLmLpWXYh1dep8u+44GQG8ClS+dv82KTKviK/cXPlfVXPFB33i/0mffN3roAAACAk5J3YgSte+DkLsay+FJAEz6nBb0sxM8M4GiBTpdk006SGRy4SDnEsRVUcP1CfgzmrrTDFGxGcsqdJJ+R5F8fBIg8Iojpl9fpcbcx6hP1TJ8vjQAuMITLrPUOWqyfn6cDuOE5urN+IbmqvtnYLwAAAMDJ0Yvk3h249f43DtvVUmWtwKiLHcDlPLpEN4XXTaTLnZuQuu0M4ML5FLSMS7CQAzdKK4FPjxD05MuoVntSpt145XU6D+DiTqPRr94OmuqffgBHx8/RvfRL7IvSN1v7BQAAADg5epHcF8DphZpfZrQCuDp/KzJAcFgCrO27LFK33rGUPco0TVPII7tN17zbI9uyELZ5aBDTK6/TW/alc9sBt+wf7ReWX635D9W99EuWJ/fNtn4BAAAATo9eJK2F1l1EaUdqObdKqxZjHqQM8ZJhqz4XGSBQO+Pteq0fYCDZtweGUjd5nHel7IcYSn4MRNZdKycI0gzMzvkypAxist5Hgw+tE08PwWgKeHXbBTOAox2tgeqlftWyh74IdZd8ri/p1dbdk71P7pdcX+4beR4AAADwouhF0grgwuLLad6wz4Ot+j1w8zxVT15uxwng5jndA1fq12U9pO7yOEL32cX659tUBYw5MKgDPFm+xZTvAaNLfGMJdKo6Bro8zO1/z2XiOn0ax7Xu1vv5zAAuvxImyG/167DKS7+eIC+hkl5t3T3Z+6j30qW+kecBAAAAL4pKAAAAAAAA50YlAAAAAACAc6MSAAAAAADAuVEJAAAAAADg3KgEAAAAAABwblQCAAAAAAA4NyoBAAAAAACcG5UAAAAAAADOjUoAAAAAAADnRiUAAAAAAIBzoxIAAAAAAMC5UQkAAAAAAODcqAQAAAAAAHBuVAIAAAAAADg3KgEAAAAAAJwblQAAAAAAAM6NSgAAAAAAACfm/wMTaHY3CO2qcQAAAABJRU5ErkJggg==>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,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>