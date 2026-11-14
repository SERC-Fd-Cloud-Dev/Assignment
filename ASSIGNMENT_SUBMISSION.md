# Submitting the Assignment

Complete each step below before the assignment deadline. Your submission ZIP should contain the repository files, the exported Postman collections (if using Postman), and the Git history.

## 1. Commit and push your work to GitHub

From the assignment repository in a terminal:

1. Check that you are in the correct repository and review the files you have changed:

   ```sh
   git status
   ```

2. Stage the assignment files you want to commit, review them, and commit:

   ```sh
   git add <file-or-folder>
   git status
   git commit -m "Complete assignment"
   ```

   Replace the placeholder with the relevant file or folder paths. Do not include passwords, access tokens, or other secrets.

3. Push all your local branches to GitHub:

   ```sh
   git push --all origin
   ```

4. Open the repository on GitHub and confirm that all expected branches and their commits are present. If you make more changes, stage and commit them, then push all branches again before continuing.

## 2. Export your Postman collections

Export each collection you need to submit as a JSON file:

1. Open Postman and select **Collections** in the sidebar.
2. Open the collection's **More actions** menu (`...`) and select **Export**.
3. Choose the recommended **Collection v2.1** format and save the JSON file in a `postman` folder in your assignment repository. Create that folder if needed.
4. Repeat for each collection. Check the exported files and replace any real credentials or tokens with placeholders.
5. On the branch containing your final assignment work, commit the exported collection files using the commands above, push all branches with `git push --all origin`, and confirm that the files appear on GitHub.

## 3. Clone the GitHub repository and create the ZIP

Do not use GitHub's **Code > Download ZIP** option: that archive contains the files but not the Git commit history. Instead, clone the pushed repository and zip the cloned folder, including its hidden `.git` folder.

1. On GitHub, open your repository, select **Code**, and copy its HTTPS URL. Note the branch containing your final work.
2. In a terminal, move to the parent folder where you want to prepare the submission, then clone the repository. Replace the example branch and URL with yours:

   ```sh
   git clone --branch main https://github.com/OWNER/REPOSITORY.git assignment-submission
   ```

3. Check that the clone includes all branches, their commits, and the exported collections:

   ```sh
   cd assignment-submission
   git branch --all
   git log --oneline --all
   ```

   The ZIP's `.git` folder preserves all fetched branches and their commit history. The visible files in the cloned folder are from the selected branch.

4. Create the ZIP on Windows using either File Explorer or the terminal:

   **File Explorer:**

   - Open File Explorer and navigate to the parent folder containing `assignment-submission`.
   - Right-click the `assignment-submission` folder. On Windows 11, select **Compress to ZIP file**; on Windows 10, select **Send to > Compressed (zipped) folder**.
   - Name the archive `assignment-submission.zip`.

   **Terminal:** Return to the parent folder and use the built-in `tar.exe` command. This creates the ZIP beside, not inside, the cloned repository:

   ```powershell
   cd ..
   tar.exe -a -c -f assignment-submission.zip assignment-submission
   ```

   Include the hidden `.git` folder in the ZIP so the commit history is preserved.

5. Open `assignment-submission.zip` and check that it contains the `.git` folder and, if using Postman, the `postman` folder with your exported collection files. If `.git` is not visible, enable **Hidden items** in File Explorer. If it is missing from the archive, use the terminal command above and check the new ZIP again.

## 4. Upload the ZIP to Moodle

1. Sign in to Moodle and open the course and assignment drop box.
2. Select **Add submission** (or the equivalent upload option), then upload `assignment-submission.zip`.
3. Save the changes. If Moodle has a separate **Submit assignment** or confirmation step, complete that as well.
4. Confirm Moodle shows the submission as submitted and check that the uploaded file is the correct ZIP.
5. Complete the upload and any required confirmation **before the assignment deadline**. Allow time for the upload to finish.
