# Bind to source control
The **Bind to Source Control** is a feature that allows users to connect their Flare projects to a version control system (VCS) such as Git or SVN. By binding a Flare project to source control, users can track changes, collaborate with team members, manage different versions of the project, and revert to previous versions if needed. This integration helps streamline the documentation workflow and maintain version history for easier project management.

## Bind project
During the process of [setting up a new project](https://github.com/mcmillanpl/Sample/new/main/tutorials/create-a-project-in-madcap), you can choose to bind your project to a source control application. 

1. From the **Start New Project Wizard** dialog box, select the **Bind to Source Control** checkbox, then select **Next**.
2. Select the **Source Control Provider** you will be using from the drop-down. Depending on the source control provider, you will be prompted to complete different processes:

### Git
1. Select the **Remote Repository** checkbox if you are binding to a remote repository. If you want to work locally, you can leave this checkbox unselected.
   - If selected, you will need to populate the address of the repository in the empty field beneath the checkbox. This will be either an HTTP or SSH URL.
2. Select the **Push on bind** checkbox if you want to push inital project files to the remote repository when you bind. 
3. Populate the **Name** and **Email** fields.
4. The **Save Per** drop-down allows you to choose how you want your files saved.
   - **User**: saves the files to your local folder. This is the best option if you are working with other tools or you want to use the same user identity across multiple projects.
   - **Project**: saves the files locally to your project. This is the best option if you need to use diffeent identities for each project.
5. Add any comments as necessary to the **Comment** field.
6. Select **OK**.
   - If you used an HTTP URL, you will be prompted to enter your user name and password. Then select **OK**
   - If you used an SSH URL, you will be prompted to enter your **Public key**, **Private key**, then select **OK**.

### Microsoft Team foundation server
1. Enter the name of the computer or server IP address in the **Server** field.
   - Select the ellipsis option to choose a **Team Project Collection**.
     - Select the green plus sign symbol.
     - Enter the name or URL of the server.
     - Enter the path and port number.
     - Select the protocol (HTTP/HTTPS)
2. Select the ellipsis option next to **Project Path** and choose the Team Foundation Server folder you want to bind the Flare project to.
3. Select **OK**.
4. You can add optional internal comments in the **Comment** field.
5. Select the **Keep files checked out** checkbox to check out the project files once you are finished.
6. Select **OK**.

### Subversion
1. Populate the **Server** field with the IP address.
2. Select the ellipsis option next to **Project Path** and choose the Subversion folder you want to bind the Flare project to.
3. Select **OK**.
4. You can add optional internal comments in the **Comment** field.
5. Select **OK**.
6. You may be prompted to log-in. If so, populate your **User name** and **Password**, then select **OK**.

### Perforce Helix Core
1. Populate the **Server** field with the server address.
2. Select the ellipsis option next to the **User** field to choose a user, then select **OK**.
3. Select to bind to a stream or depot from the **Type** drop-down.
   - If you are binding to a stream, select **New** next to the Stream field.
     - You may be prompted to log-in with your **User name** and **Password** fields, then select **OK**.
     - Select the type of stream from the **Stream Type** drop-down.
     - Choose a depot by selecting **Browse** next to the **Streams Depot** field. A depot acts as a folder in Perforce Helix Core that contains multiple streams, including your Flare files.
     - Select **OK**.
     - In the **New Stream** window, you can complete any of the other optional fields. Then select **OK**.
   - If you are binding to a depot, select **New** next to the **Depot** field or choose an existing depot using the drop-down menu. Selecting **New** opens the New Depot window.
     - Populate the **Name** and **Description** fields, then select **OK**.
     - Select the ellipsis option next to **Path** and choose the location you want to bind the Flare project to. You may be prompted to log-in.
     - Select **OK**.
4. You can add optional internal comments in the **Comment** field.
5. Select the **Keep files checked out** checkbox to check out the project files once you are finished.
6. Select **OK**.
