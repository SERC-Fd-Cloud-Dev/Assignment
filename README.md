# Cloud Development Assignment

Repository and development environment configured for the Cloud Development assignment.

See [Development Environment](DEVELOPMENT_ENVIRONMENT.md) for an overview of the provided development environment features. [Assignment Submission](ASSIGNMENT_SUBMISSION.md) contains instructions for submitting your work, including saving your assignment work, preparing the submission ZIP, and uploading it to Moodle.

> Replace this README with your own instructions for setting up and running your assignment.

## If you started the assignment in another Git repository

Use these steps only if you started the assignment in a different Git repository and now want to add that repository's work to this GitHub repository. If you have been working in this repository already, you do not need to follow these steps.

Because this GitHub repository may already contain files (for example, an initial README), merge its history into your existing local repository before pushing. This preserves files from both repositories instead of overwriting the GitHub repository.

1. Make sure your local work is committed, and create a backup if needed.
2. In your existing local repository, add the GitHub repository as a remote and fetch its branches:

   ```sh
   git remote add github https://github.com/OWNER/REPOSITORY.git
   git fetch github
   ```

   Replace the URL with your repository's URL. If you already have a remote named `github`, update it with `git remote set-url github <URL>` instead.
3. Check the GitHub repository's default branch with `git branch -r`. The commands below use `main`; substitute the correct branch name if it is different.
4. Merge that branch into your current local branch:

   ```sh
   git merge github/main --allow-unrelated-histories
   ```

   If Git reports conflicts, resolve them deliberately: keep or combine the content you need from each side, then run `git add <files>` and `git commit`. Git does not silently replace conflicting files during this merge.
5. Push the merged history to the GitHub default branch:

   ```sh
   git push github HEAD:main
   ```

   Do not use `git push --force`; force-pushing can discard commits already on GitHub.
