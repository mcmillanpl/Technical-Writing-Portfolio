# Create a project in MadCap Flare

In Flare, a **Project** is a collection of files and resources used to create and manage specific outputs, such as documentation sets or online help systems. It includes topics, stylesheets, images, and configuration files, enabling you to organize, author, and publish content efficiently.

## Prerequisites
Before you begin, ensure you have the following:

- **MadCap Flare** installed and licensed.
- **Ghostscript** installed (Required for handling PDF and EPS files).

## Create a new project
1. Select **New Project** from the Start Page, or go to **File > New Project** in the top ribbon.
2. Complete the fields in the **Start New Project Wizard**, then select **Next**:
   - **Project Name**: The display name of your project.
   - **Project Folder**: The local directory where project files will be stored.
   - **Language**: The primary language for the project content.
   - **Bind to Source Control**: (Optional) Integrates the project with Git or SVN. For setup instructions, see [Bind to Source Control](https://github.com/mcmillanpl/Sample/blob/main/tutorials/madcap-bind-to-source-control.md).
3. Choose a project template and select **Next**:
   - **New from template**: Start with a pre-configured factory template or a custom template.
   - **New from existing**: Use a previous Flare project as the foundation.
   - **New from import**: Import legacy files (e.g., Word, Excel, FrameMaker) to seed your project.
4. If prompted, select your initial branding elements (colors, fonts, and logo). Note: You can refine these later in the **Branding Editor**. Select **Next**.
5. Choose the **Primary Target** and select **Finish**.
   - **Note on Targets:** A Target is a specific instance of an output (e.g., HTML5, PDF, or Word). You can create multiple targets within one project and change the primary selection at any time.

Your project is now created. You can begin adding topics and building your Table of Contents (TOC).

---

## Related pages
- [Connect MadCap Flare to GitHub](https://github.com/mcmillanpl/Sample/blob/main/tutorials/connect-madcap-github.md)
- [Import an existing MadCap project from GitHub](https://github.com/mcmillanpl/Sample/blob/main/tutorials/import-existing-madcap-to-git.md)