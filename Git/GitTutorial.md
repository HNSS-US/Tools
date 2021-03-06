#### Git Tutorial for Beginners - Crash Course 
##### Table of contents
1. [Introduction](#introduction)  
2. Instru
3. Troubleshooting  
   3.1 [File was deleted via command line](#TS1)  
       error: *Changes not staged for commit:*

**1. Introduction**  <a name="introduction"></a>
Git is a type of version control. Version control allows you to 
store your progress in a type of "database".
Diagram:  
![etower](https://www.git-tower.com/learn/media/pages/git/ebook/en/command-line/basics/what-is-version-control/1234869142-1570000299/what-is-vcs.png "etower")  
The advantage to using version control is you are able to go back in time to  
see the changes made to a project. For example, you changed a program and  
want to revert back to what was done. Version controlworks whether working   
alone or in a group.
**Steps** <a name="steps"></a>
**synch local directory with Github**   <a name="synchGithub"></a>
I have information saved on Github, but not to a local repository.  
I am going to create the local repository to update Github.  

<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~ $</b></font> git clone https://github.com/HNSS-US/DelTech.git
Cloning into &apos;DelTech&apos;...
remote: Enumerating objects: 101, done.
remote: Counting objects: 100% (101/101), done.
remote: Compressing objects: 100% (99/99), done.
remote: Total 656 (delta 43), reused 0 (delta 0), pack-reused 555
Receiving objects: 100% (656/656), 1.00 MiB | 9.61 MiB/s, done.
Resolving deltas: 100% (278/278), done.
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~ $</b></font> </pre>  






*********** TODO  New Repository ************************************

**2.0 Created directory DelTech**
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~ $</b></font> mkdir DelTech
</pre>  

**2.1 Current directory structure**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> ls -alF
total 24
drwxrwxr-x  2 james james  4096 Oct  5 23:25 <font color="#729FCF"><b>.</b></font>/
drwx------ 61 james james 20480 Oct  5 23:25 <font color="#729FCF"><b>..</b></font>/
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.2 Create local git repository**  
 <pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git init
Initialized empty Git repository in /home/james/DelTech/.git/
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
Listing the directory again shows new file:  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> ls -alF
total 28
drwxrwxr-x  3 james james  4096 Oct  5 23:34 <font color="#729FCF"><b>.</b></font>/
drwx------ 61 james james 20480 Oct  5 23:25 <font color="#729FCF"><b>..</b></font>/
drwxrwxr-x  7 james james  4096 Oct  5 23:34 <font color="#729FCF"><b>.git</b></font>/
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.3 Ignoring files**  
At the start of creating the repository, I know I do not want to   
use version control on certain files. For example, I do not  
want .pdf files versioned. Therefore, create a file  
called ".gitignore". Then add the file(s) to ignore.  
For:  
- Ignore one specific file: Provide the full path to the file, seen   
  from the root folder of your project.  
  **path/to/file.ext**  
- Ignore all files with a certain name (anywhere in the project):  
  Just write down the file's name, without giving a path.  
  **filename.ext**  
- Ignore all files of a certain type (anywhere in the project):  
  ***.ext**  
  <pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> vi .gitignore</pre>  
 **2.4 Making first commit**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git add -A
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git commit -m &quot;Inital Commit DelTech&quot;
[master (root-commit) ea9d301] Inital Commit DelTech
 1 file changed, 1 insertion(+)
 create mode 100644 .gitignore
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.3 Checking status of Git Repository**    
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git status
On branch master
nothing to commit, working tree clean
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>    
**2.4 Checking status of log** 
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git log
<font color="#C4A000">commit ea9d3018b81b82c96e5261e62a091cf0d7756f53 (</font><font color="#34E2E2"><b>HEAD -&gt; </b></font><font color="#8AE234"><b>master</b></font><font color="#C4A000">)</font>
Author: HNSS-US &lt;james@T420&gt;
Date:   Sat Oct 5 23:46:25 2019 -0400

    Inital Commit DelTech
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.5 Now adding repository from Github**  
*(Notice: There is no response after running this command. Also, I had a lot of files 
and this took a few seconds. Here the ".", adds everything in the directory and below to git.)*  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git add .
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> </pre>  
**2.6 Repeating *git log* and *git status* is the same as before.**  
**2.7 Commiting to Git with "comment"**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git commit -m &quot;creation of git&quot;
[master (root-commit) 3f2d714] creation of git
 159 files changed, 179954 insertions(+)
 create mode 100644 CSC/CSC114/Assignment0/Assignment0.odt
 create mode 100644 CSC/CSC114/Assignment0/CSC114Assignment0_Ethics.pdf
 create mode 100644 CSC/CSC114/Assignment1/.vscode/tasks.json
 create mode 100644 CSC/CSC114/Assignment1/Assignment1.zip
 .
 .
 .
 create mode 100644 HIS/HIS111/Zip_Files/HIST, Comprehensive 5th Edition by Kevin M. Schultz sm.zip
 create mode 100644 HIS/HIS111/Zip_Files/HIST, Comprehensive 5th Edition by Kevin M. Schultz_test_bank.zip
 create mode 100644 README.md
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.8 Checking status of log**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git log
<font color="#C4A000">commit 3f2d714968fcb87dfc13d008fa0ca2f813c1623c (</font><font color="#34E2E2"><b>HEAD -&gt; </b></font><font color="#8AE234"><b>master</b></font><font color="#C4A000">)</font>
Author: HNSS-US &lt;james@T420&gt;
Date:   Thu Sep 26 18:51:48 2019 -0400

    creation of git
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font></pre>  
**2.9 Check Status**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> git status
On branch master
nothing to commit, working tree clean
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech $</b></font> 
</pre>  
**2.10 Git branch diagram**  
The following diagram shows what we have 
done and what we are about to do  
Git branching:  
![git branch](https://guides.github.com/activities/hello-world/branching.png "Git Branch Image")  
**2.11 Working with one file**

### 3 Troubleshooting  
**3.1 File was deleted via command line, now unable to have it sync with Git <a name="TS1"></a>  
      Changes not staged for commit:**  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/Textbooks $</b></font> rm text.txt</pre>  
##### After completing Assignment4, checked Git status
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font> git status  
On branch master  
Changes to be committed:
  (use &quot;git reset HEAD &lt;file&gt;...&quot; to unstage)
	<font color="#4E9A06">modified:   .vscode/tasks.json</font>
	<font color="#4E9A06">new file:   Assignment4.zip</font>
	<font color="#4E9A06">new file:   distance_traveled5_6</font>
	<font color="#4E9A06">modified:   distance_traveled5_6.cpp</font>
	<font color="#4E9A06">new file:   membership_fee_increase5_5</font>
	<font color="#4E9A06">modified:   membership_fee_increase5_5.cpp</font>
	<font color="#4E9A06">new file:   sum_numbers5_1</font>
	<font color="#4E9A06">modified:   sum_numbers5_1.cpp</font>
Changes not staged for commit:
  (use &quot;git add/rm &lt;file&gt;...&quot; to update what will be committed)
  (use &quot;git checkout -- &lt;file&gt;...&quot; to discard changes in working directory)

	<font color="#CC0000">deleted:    ../../Textbooks/dropped text.txt</font>

<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font></pre>  
##### Commited to 
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font> git commit -m &quot;Assignment4&quot;
[master b3aa52c] Assignment4
 8 files changed, 244 insertions(+), 82 deletions(-)
 create mode 100644 CSC/CSC114/Assignment4/Assignment4.zip
 create mode 100755 CSC/CSC114/Assignment4/distance_traveled5_6
 create mode 100755 CSC/CSC114/Assignment4/membership_fee_increase5_5
 create mode 100755 CSC/CSC114/Assignment4/sum_numbers5_1
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font></pre>  

##### Checked Git status  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font> git status
On branch master
Changes not staged for commit:
  (use &quot;git add/rm &lt;file&gt;...&quot; to update what will be committed)
  (use &quot;git checkout -- &lt;file&gt;...&quot; to discard changes in working directory)

	<font color="#CC0000">deleted:    ../../Textbooks/dropped text.txt</font>

no changes added to commit (use &quot;git add&quot; and/or &quot;git commit -a&quot;)
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/CSC114/Assignment4 $</b></font> </pre>  
##### To remove  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/Textbooks $</b></font> git add -u .
<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/Textbooks $</b></font></pre>  

##### Corrected  
<pre><font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/Textbooks $</b></font> git status
On branch master
Changes to be committed:
  (use &quot;git reset HEAD &lt;file&gt;...&quot; to unstage)

	<font color="#4E9A06">deleted:    dropped text.txt</font>

<font color="#8AE234"><b>james@T420</b></font> <font color="#729FCF"><b>~/DelTech/CSC/Textbooks $</b></font> 
</pre>  

##### [Back to top](#introduction)  
