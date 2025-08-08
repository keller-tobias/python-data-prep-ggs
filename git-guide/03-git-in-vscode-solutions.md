# Using Git in VS Code - Solutions

## Solutions to Exercises

### Exercise 1:

1. Make changes to multiple files in your project:
   ```bash
   echo "Change 1" >> file1.txt
   echo "Change 2" >> file2.txt
   ```
2. Use the Source Control panel to stage only some of the files:
   - Click the `+` icon next to `file1.txt` to stage it.
3. Commit the staged files with a descriptive message:
   - Type "Staged file1.txt" in the commit message box and click the checkmark.
4. Stage and commit the remaining files separately:
   - Stage `file2.txt` and commit it with the message "Staged file2.txt".
5. Compare how this differs from using command line Git:
   - Using the command line, you would use `git add file1.txt` and `git commit -m "Staged file1.txt"`.

### Exercise 2:

1. Create a new branch called `vscode-practice` using the VS Code interface:
   - Click the branch name in the bottom-left corner.
   - Select "Create new branch..." and name it `vscode-practice`.
2. Make some changes and commit them:
   ```bash
   echo "VS Code practice changes." >> practice.txt
   git add practice.txt
   git commit -m "Added practice.txt"
   ```
3. Switch back to the main branch:
   - Click the branch name in the bottom-left corner and select `main`.
4. Notice how VS Code automatically updates your files when switching branches.
5. Merge the `vscode-practice` branch back into main:
   - Use the "..." menu in the Source Control panel, select "Branch" → "Merge Branch...", and choose `vscode-practice`.
