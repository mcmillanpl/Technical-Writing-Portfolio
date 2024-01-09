# Connect MadCap Flare to Git
This tutorial outlines the steps needed to connect Madcap Flare to GitHub. After connecting your project in Git, you will be able to commit all your changes to Git and sync the repository with any MadCap Flare project. 

Connecting MadCap Flare to Git can provide several benefits, such as allowing the documentation team to leverage version control, enabling them to track changes, collaborate easily, and roll back to previous versions if needed. Additionally, it streamlines the review and approval process by providing a centralized platform for team members to contribute, comment, and merge changes. 

## Prerequisites
Before you begin, you will need to have the following:

- A GitHub account.
- Git installed/configured on your local computer.
- Have MadCap Flare installed on your computer.

## Connect a local MadCap project to GitHub
1. Create a new, empty, repository in GitHub.
2. Copy the SSH link that is automatically created with the new repository.
3. In MadCap Flare, open **Project** and select **Project Properties**.
4. Open **Source Control** and select **Bind Project**
5. Select **Git** as the "source control provider" from the drop-down.
6. Select the **Remote Repository** checkbox to make it true.
7. Paste the SSH link you copied into the blank field below **Push on bind**.
8. Enter your name, email address, then select **OK**.
   ![image](https://github.com/mcmillanpl/Sample/assets/156026947/22c739e4-b687-4bda-8dc4-3041c4a7764c)

9. Review the details of your project in the **Project Properties** window, then select **OK**.
10. Refresh the GitHub repository page to see the changes.

The local project has now been uploaded to the empty repository. Now changes to your local files in MadCap Flare can be committed and pushed to this new repository. 

### Related pages
- [Import an existing MadCap project from Git](https://github.com/mcmillanpl/Sample/edit/main/tutorials/import-existing-madcap-to-git.md)
