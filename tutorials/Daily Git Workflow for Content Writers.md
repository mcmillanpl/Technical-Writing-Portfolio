# Daily Git Workflow for Content Writers

Once your project is bound to Git, follow this daily "Sync-Edit-Sync" workflow to ensure your local files are up to date and your changes are safely backed up to the remote repository.

---

## 1. Start of Day: Update Local Files
Before you begin writing, always pull the latest changes from the team to avoid merge conflicts.

1. Open your project in MadCap Flare.
2. In the **Source Control** ribbon, select **Pull**.
3. If Flare indicates your local files are up to date, you are ready to work.

## 2. During the Day: Edit and Save
Work on your topics as usual. 
* **Tip:** Save your work frequently (`Ctrl+S`). Flare tracks changes locally as soon as a file is modified.

## 3. End of Task: Commit and Push
Once you have finished a specific topic or a set of related updates, send them to the remote repository.

1. **Commit (Local Save):**
   - Go to the **Source Control** ribbon and select **Commit**.
   - Select the files you want to include.
   - Enter a clear **Commit Message** (e.g., `docs: updated installation requirements`).
   - Select **Commit**.

2. **Push (Upload to GitHub):**
   - In the **Source Control** ribbon, select **Push**.
   - This uploads your local commits to the GitHub repository so your team can see them.

---

## Workflow Summary Table

| Action | Frequency | Purpose |
| :--- | :--- | :--- |
| **Pull** | Every Morning | Syncs your computer with the team's latest work. |
| **Commit** | After every task | "Checkpoints" your work locally with a descriptive note. |
| **Push** | End of day / task | Backs up your work to the server and shares it with others. |

---

## Conflict Resolution
If you see a **Merge Conflict** message during a Pull or Push, it means another writer edited the same line of code as you.
1. Select **Resolve** in the Flare dialog box.
2. Choose **Merge Changes in Tool** to see the differences side-by-side.
3. Accept the correct version and click **Save**.