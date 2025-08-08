# Collaboration with Remote Repositories - Solutions

## Solutions to Exercises

### Exercise 1:

1. Create a new repository on GitHub called `git-exercise`.
2. Connect your local repository to this new remote:
   ```bash
   git remote add origin https://github.com/your-username/git-exercise.git
   ```
3. Push all your existing commits to GitHub:
   ```bash
   git push -u origin main
   ```
4. Verify that all your files and commit history appear on GitHub by visiting the repository page.

### Exercise 2:

1. Edit a file directly on GitHub through the web interface:
   - Navigate to one of your files on GitHub.
   - Click the pencil icon to edit.
   - Make a small change and commit it through the web interface.
2. Make another local change to a different file:
   ```bash
   echo "Local change." >> local_file.txt
   git add local_file.txt
   git commit -m "Added local change"
   ```
3. Try to push your local changes (this should fail):
   ```bash
   git push
   ```
4. Pull the remote changes first, then push your local changes:
   ```bash
   git pull
   git push
   ```
5. Verify both changes are present locally and remotely by checking the files and commit history.
