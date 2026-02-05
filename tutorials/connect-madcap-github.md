# Connect an existing MadCap Flare project to Git

This tutorial outlines the steps to connect a local MadCap Flare project to a remote GitHub repository. Connecting your project to Git allows your documentation team to leverage version control, track changes, collaborate seamlessly, and roll back to previous versions if needed.

## Prerequisites
Before you begin, ensure you have the following:

- A GitHub account.
- **Git** installed and configured on your local computer.
- **MadCap Flare** installed.

## Connect a local MadCap project to GitHub
1. Log in to GitHub and create a new, **empty** repository. Do not initialize it with a README or .gitignore yet (Flare will handle this).
2. Copy the **HTTPS** or **SSH** link provided in the "Quick Setup" section of the new repository.
3. Open your project in MadCap Flare.
4. Select the **Project** tab from the ribbon and select **Project Properties**.
5. Select the **Source Control** tab and click **Bind Project**.
6. Select **Git** as the source control provider from the drop-down menu.
7. Select the **Remote Repository** checkbox.
8. Paste the URL you copied in Step 2 into the **Remote Repository** field. 
9. Enter your **Name** and **Email address**, then select **OK**.
10. Review the project details in the **Project Properties** window, then select **OK**.
    - **Note (HTTPS):** You will be prompted to log in. You must use a **Personal Access Token (PAT)** rather than your GitHub password.
    - **Note (SSH):** You may be prompted to provide the path to your public and private keys.
11. Refresh your GitHub repository page in your browser to verify that your files have uploaded.

The local project is now bound to the remote repository. You can now use the **Source Control** ribbon in Flare to Commit and Push your changes.

---

### Related pages
- [Import an existing MadCap project from Git](https://github.com/mcmillanpl/Sample/blob/main/tutorials/import-existing-madcap-to-git.md)
- [Daily Git Workflow for Writers](https://github.com/mcmillanpl/Sample/blob/main/tutorials/daily-git-workflow.md)