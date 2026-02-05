# Import an existing MadCap project from Git

This tutorial outlines the steps to import an existing MadCap project from Git to your local computer. This process—commonly referred to as "cloning"—allows you to collaborate on a shared project, maintain version history, and reuse established styles and content across your team.

## Prerequisites
Before you begin, ensure you have the following:

- A GitHub account with access to the project repository.
- Git installed and configured on your local computer.
- MadCap Flare installed.
- The SSH or HTTPS URL for the target repository.

## Import existing project
1. Navigate to the GitHub repository containing the MadCap Flare project you want to import.
2. Select the **Code** button and copy the **SSH** or **HTTPS** link.
3. In MadCap Flare, select the **File** menu, then select **New Project**.
4. Select **Import From Source Control**.
5. In the **Import Project From Source Control Wizard**, select **Git** as the provider and paste the copied link into the **Remote Repository** field.
6. Select **Next**.
   - *Note: If using SSH for the first time, you may be prompted to point Flare to your private key file.*
7. Select **Browse**, then locate and select the `.flprj` (Flare Project) file from the remote repository list. Select **OK**.
8. Select **Next**, then review the **Project Name** and the **Project Folder** (where the files will live on your hard drive). 
9. Select **Finish**.

The MadCap project will now be downloaded to your local computer and remains "bound" to the remote repository, allowing you to Pull updates and Push changes.

---

## Troubleshooting Common Import Errors

| Error | Cause | Resolution |
| :--- | :--- | :--- |
| **Permission Denied (publickey)** | SSH Key Mismatch | Ensure your SSH public key is added to your GitHub account settings. In Flare, verify you have selected the correct private key file. |
| **Repository Not Found** | Incorrect URL | Double-check that you copied the full URL (ending in `.git`) and that you have "Read" access to that specific repository. |
| **Empty Project List** | Missing `.flprj` file | Ensure the repository actually contains a Flare project file. If the project is in a subfolder, you must navigate into that folder during the "Browse" step. |
| **SSL Certificate Problem** | Network/Firewall | If using HTTPS, your company's firewall may be intercepting the connection. Try switching to SSH or contact your IT department. |

---

## Related pages
- [Connect MadCap Flare to Git](https://github.com/mcmillanpl/Sample/blob/main/tutorials/connect-madcap-github.md)
- [Bind an existing project to Source Control](https://github.com/mcmillanpl/Sample/blob/main/tutorials/bind-to-source-control.md)