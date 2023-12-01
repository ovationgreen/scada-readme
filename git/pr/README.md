# Ovation Green
Pull requests are used to commit changes to the GitHub repository and track the process of task completion.
Here are the key stages of this process:
1.	Create a branch for a Jira task you receive. 
2.	Make changes in relation to your Jira task and commit these changes. 
3.	Create a pull request, assign reviewers, and request reviews from them.
4.	Receive comments from reviewers, implement the relevant ones, and commit changes (this step repeats as many times as needed to fully complete the task.) 
5.	After reviewers approve your changes, merge your branch with the original branch.
See the following sections for more details.
## Create a branch for a pull request
### Create a branch in GitHub Web
1.	On the page of the Jira task you are about to start working on, change the status to **In Progress**. 
2.	In the **To Do** section, **Development** field, click **Create branch**.
![create a branch_1](https://github.com/ovationgreen/scada-readme/assets/150123119/462b1c10-0260-4dcc-9e6e-26f98d0bc6c1)
3.	On the **Create GitHub Branch** page, in the **Repository** field, select the repository to commit the changes to.

_**Note:**_ 
Repositories:

•	_scada-pc_—for storing all source files.

•	_scada-lib_—for storing additional libraries.

4.	In the **Branch from** field, select the original branch for your new branch.
   
_**Note:**_ It should be the branch that is named on your Jira task page > **Details** section > **Fix versions**. 
![Fix version](https://github.com/ovationgreen/scada-readme/assets/150123119/ab94aa4e-afbb-45a9-bd08-811e35efd6e7)

5.	In the **Branch name** field, view a proposed name for your branch and change it if needed.

_**Note:**_ 
Follow the `SCADA-0000-Name-of-your-task` name format where 0000 is the number of your JIRA task and Name-of-your-task is its name.
7.	Click **Create branch**.
   
![create a branch_2](https://github.com/ovationgreen/scada-readme/assets/150123119/a64f3bdb-ec71-45a6-b208-fb2c6945df82)

_**Note:**_ 
Click **View branch in GitHub** to open the branch page.
After you successfully create the branch, you will receive a corresponding notification and will be able to view the branch at the page of the related Jira task.
![create a branch_3](https://github.com/ovationgreen/scada-readme/assets/150123119/974731ea-3e26-4b13-9f75-71d96b12ee70)
### Create a branch in GitHub Desktop
1.	In GitHub Desktop, in the **Current branch** tab, open the **Branches** dropdown and select the branch that will become original for your new branch. 
![Create a branch_desktop_1](https://github.com/ovationgreen/scada-readme/assets/150123119/7517c95c-e638-4f28-81f2-69a2a7913a02)
_**Note:**_ It should be the branch that is named on your Jira task page > **Details** section > **Fix versions**. 
![Fix version](https://github.com/ovationgreen/scada-readme/assets/150123119/ab94aa4e-afbb-45a9-bd08-811e35efd6e7)
2.	In the **Fetch origin** tab, make sure that all your files are synchronized.
![Create a branch_desktop_2](https://github.com/ovationgreen/scada-readme/assets/150123119/b4cbde0d-ed56-4488-8f00-31970c54e2db)
3.	On the top panel, click **Branch** and select **New branch…** from the drop-down menu. 
![Create a branch_desktop_3](https://github.com/ovationgreen/scada-readme/assets/150123119/50dfee2a-fec4-4e1e-a66a-33151066fab3)
4.	In the **Create a branch** pop-up window, provide the needed information:
   
a.	In the **Name** field, provide the name for your branch. 

b.	In the **Create branch based on…** section, select the original branch for your newly created one.

6.	Click **Create branch**.
	
![Create a branch_desktop_4](https://github.com/ovationgreen/scada-readme/assets/150123119/78d4c5af-84c6-40d3-ba9c-f62fbb9d8b7c)
After that, you can publish your branch to a remote repository and start making changes to it.
## Fetch a branch 
_**Note:**_ 
It is only relevant for when you have created a branch in the GitHub web application; when you create a branch in the GitHub desktop application, you fetch files within the branch creation process.
Before making any changes, you need to fetch your branch to download all the original branch files from the remote repository to your local repository. 
For that:
1.	Run the **cmd** terminal. 
2.	Type in `git fetch` and press **Enter** to run the fetch command.
## Check out a branch
_**Note:**_  
It is only relevant for when you have created a branch in the GitHub web application; when you create a branch in the GitHub desktop application, you fetch files within the branch creation process.
After your branch is synchronized with the original one, perform the checkout to switch to your new branch for any further changes.
For that:
1.	Run the **cmd** terminal.
2.	Type in `git checkout`, insert your branch name from the console, and press **Enter** to run the command. 
Now, the branch is visible in your Workpace source tree and you can work on your task. 

## Create a commit and push changes
When you make the needed changes, you can create a commit and push the changes.

    
        
          
    

        
        Expand All
    
    @@ -111,7 +111,7 @@ You can also stage a part of a file. One option is to stage a hunk of a file by
  
For that:
1.	Open your branch in your Workspace source tree.
2.	In the **Unstaged files** section, click a changed file to review the changes made to your branch in comparison to the original branch.  
![Stage changes_1](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/e93282ea-e1d1-4b74-b753-a21a3122b292)
3.	Stage the changed files by doing either of these:
   
a)	Click the plus button near the updated file. 
b)	Select a file or several files and click **Stage Selected**.
c)	If you want to stage all the listed files, click **Stage All**. 
![Stage changes_2](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/a18dc96e-d585-4eb9-bb29-e6c4930112d0)
_**Note:**_  
You can also stage a part of a file. One option is to stage a hunk of a file by clicking **Stage hunk**. 

![Stage changes_3](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/b47a9c6d-e708-46d0-ab7c-feb4af5c8285)

Another option is to stage a line or several lines of a file by selecting the needed lines and clicking **Stage lines**.

![Stage changes_4](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/bec57faa-ab90-4628-a5b0-466c2d2347bc)


    
          
            
    

          
          Expand Down
    
    
  
4.	In the **Commit** message box at the bottom of the page, provide a summary of your changes starting with the Jira task number in the `SCADA-5811` format. 
5.	Click **Commit**. 
![Commit changes](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/9e772847-4dbf-4552-bbcb-b7f29df6a426)
6.	On the toolbar, click **Push** to see the branches that are available to push. 
![Push changes_1](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/8a44a677-de23-4e08-9999-18867d02a352)
7.	In the **Push:** dialog, in the **Push?** tab, select the checkbox near the needed branch. 
8.	Click **Push**.  
![Push changes_2](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/07bce53f-5cca-4f33-a47f-e1a0ee3fa57d)
## Create a pull request
After you make changes and push your commit, it is time to create a pull request to include these changes in the original branch. For that: 
1.	At GitHub, in the **Switch branches/tags** dropdown menu, find your branch and click it.
![View a branch](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/aaba4907-40ab-4453-aaa3-017adf1eee14)
2.	On the page of your branch:
   
a.	Click **Contribute** to open a dialog and click **Open pull request**.
b.	Or click **Compare & pull request**.
![Create a pull request_1](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/c348cc1b-9bb5-4542-9936-a857a517da7b)
3.	On the **Open a pull request** page, provide all the necessary information:
a.	From the **base:** dropdown list, select the branch to pull your changes in.
b.	In the **Add a title** field, enter the name of the Jira task that your changes relate to. 
c.	In the **Add a description** section, provide a link to the Jira task that this pull request relates to and the task description. If there are any relevant images or other files, add them as well, so that the pull request reviewers will be able to quickly grab the gist of your task.
d.	In the **Reviewers** section, select the needed reviewers from the dropdown list. 
_**Note:**_  
People who are assigned as reviewers can assign other reviewers if they think that additional input would help.
_**Note:**_
Make sure to include these roles to cover all the key aspects of your changes: 
•	Reviewer. 
•	Tester reviewer.
•	Technical writer—in case there is a need to verify the quality of the UI text.
e.	In the **Labels** section, from the dropdown list, select the label that corresponds your current release. It is needed for better navigation.
_**Note:**_  
You can also provide other information if relevant.
4.	Click **Create pull request**.
 
![Create a pull request_2](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/4343ec5d-2631-492a-b7cd-56763a9a2884)
_**Note:**_ 
There is also the **Create draft pull request** option which is used in case you have not finished a task yet but want the reviewers to take a look at it. 
## Work with reviewers' comments 
_**Note:**_ 
When you send a pull request for review, you should make the corresponding marking on the page of the related Jira task. 
For that:
1.	Change the status of the Jira task to **Waiting for Test**.
2.	In the **Assignee** field, change your name to the name of the tester who is to review your work.
![Waiting for test Jira status](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/86eaf9ce-4070-4517-aebd-c6e78015e1ea)
When all the comments are resolved, the tester closes the Jira task.
Reviewers may leave comments to your pull request asking you to fix some bugs or make another improvement to your pull request. You will see such comments with the corresponding red icon (a) in the **Reviewers** or **Changes requested** section. 
In case the fix is needed, you should:
1.	Make the needed changes and create another commit for your pull request.
2.	On the page of the pull request, reply to the reviewer’s comment letting them know about your fix.
3.	Click **Re-request review** (b) near the name of the reviewer who has requested the changes to ask them to review the pull request once again. 
When reviewers approve all your changes, you will see the corresponding green icon (c) in the **Reviewers** or **Changes requested** section.
![Work with reviewers' comments](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/4ed1418e-ef6d-4ea0-8af6-3bd327bbb555)
_**Note:**_ 
A comment can be resolved only by the person who creates it. You cannot resolve a reviewer’s comment by yourself even after you make the required changes. Instead, leave your own comment to let the reviewer know that you are working on the improvement or have already finished it. 
The only exception is the case when a reviewer who has left unresolved comments has already approved the pull request. Then, you are supposed to close the unresolved comments because otherwise, you may be unable to merge a pull request with active conversations. 
_**Note:**_
You have to wait for all reviewers to approve your pull request before merging it. The only exception is a tester if you have selected more than one of them as your reviewer. 
## Create an issue for a pull request 
_**Note:**_
View [this manual](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue) to learn how to link an issue to a pull request.
In case there are plenty of issues related to a pull request or the comments are not enough to highlight all the necessary changes, a tester may create an issue for a pull request in GitHub. 
For that:
1.	On the GitHub repository page, click **Issues**. 
2.	On the **Issues** page, click **New issue**. 
![Create an issue_1](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/97bb8023-66e9-4fb7-a03a-5f254968ba0c)
3.	On the **New issue** page, provide the needed information:
   
a.	In the **Title** field, provide a title for the issue that grasps the main point of it.
b.	In the **Add a description** field, provide a link to the pull request that is associated with this issue and an explanation of the needed fixes. 
5.	Click **Submit new issue**.
_**Note:**_
A developer is supposed to convert the pull request associated with an issue or issues to a draft pull request, fix all of the issues, and close them as fixes. 
Only after that, they can mark a pull request as **Ready for review** and re-request review from their reviewers. 
## Convert a pull request to draft
In case there are too many comments from reviewers or issues associated with your pull request, you may need to convert it to a draft to make all the necessary fixes.
For that, on the page of the pull request, under the **Reviewers** section, click **Convert to draft**.
![Convert to draft](https://github.com/Alla-Vashchuk/scada-readme/assets/150123119/7024760b-9671-4759-8cd8-54e08153f759)
## Merge a pull request
After all the reviewers approve your pull request, it is time to merge it.
For that:
1.	In the **Changes approved** section, open the **Merge pull request** dropdown menu.
2.	Select:
   
a.	**Create merge commit**—to save your entire history of commits available for viewing (this option is only used in case several developers are working on this pull request and you want to track their separate changes.)
b.	**Squash and merge**—to connect all your commits into a single one and add it to the original branch.
After you merge a pull request, the branch that was created to make these changes is deleted from the repository automatically.
## Avoid version conflicts after merging a pull request
After you merge a pull request with a certain branch, for example, 5.8, you need to make sure that there are no conflicts with merging this branch with the next one, for example, 5.8.1. 
In case there are conflicts or required changes, you need to create a new pull request for merging this release with another (5.8.1) branch. 
