# Git Intro: Basic Workflow, Branching, and .gitignore - Solutions

## Solutions to Exercises

### Exercise 1:

1. Create a new file `second_file.txt` with some text:
   ```bash
   echo "This is the second file." > second_file.txt
   ```
2. Stage this new file:
   ```bash
   git add second_file.txt
   ```
3. Commit it with a message:
   ```bash
   git commit -m "Added second_file.txt"
   ```
4. Modify `second_file.txt` and stage the changes:
   ```bash
   echo "Adding more content." >> second_file.txt
   git add second_file.txt
   ```
5. Modify `hello.txt` again and stage the changes:
   ```bash
   echo "Another line in hello.txt." >> hello.txt
   git add hello.txt
   ```
6. Commit both changes together with a single commit message:
   ```bash
   git commit -m "Updated second_file.txt and hello.txt"
   ```

### Exercise 2:

1. Modify `second_file.txt` and stage the changes:
   ```bash
   echo "Temporary changes." >> second_file.txt
   git add second_file.txt
   ```
2. Unstage the changes:
   ```bash
   git restore --staged second_file.txt
   ```
3. Discard the changes in `second_file.txt`:
   ```bash
   git restore second_file.txt
   ```
4. Modify `second_file.txt` again:
   ```bash
   echo "Final changes." >> second_file.txt
   ```
5. Add a new file `third_file.txt` with some text:
   ```bash
   echo "This is the third file." > third_file.txt
   ```
6. Stage both files:
   ```bash
   git add second_file.txt third_file.txt
   ```
7. Commit both files together with a message:
   ```bash
   git commit -m "Added third_file.txt and updated second_file.txt"
   ```
8. Make a change to `third_file.txt` and stage the changes:
   ```bash
   echo "Another line in third_file.txt." >> third_file.txt
   git add third_file.txt
   ```
9. Undo the last commit using `--soft` and check the status:
   ```bash
   git reset --soft HEAD~1
   git status
   ```
10. Undo the last commit using `--hard` and check the status:
    ```bash
    git reset --hard HEAD~1
    git status
    ```

###  Exercise 3:

1. Create a new branch called `feature-2`:
   ```bash
   git switch -c feature-2
   ```
2. Add a new file `feature2.txt` with some text:
   ```bash
   echo "This is feature 2." > feature2.txt
   ```
3. Stage and commit the new file:
   ```bash
   git add feature2.txt
   git commit -m "Added feature2.txt"
   ```
4. Switch back to the `main` branch:
   ```bash
   git switch main
   ```
5. Modify `hello.txt` by adding another line and commit the changes:
   ```bash
   echo "Another line in main branch." >> hello.txt
   git add hello.txt
   git commit -m "Updated hello.txt in main branch"
   ```
6. Merge the `feature-2` branch into `main`:
   ```bash
   git merge feature-2
   ```
7. Resolve any merge conflicts if they occur.
8. View the commit history to verify the merge:
   ```bash
   git log --oneline --graph
   ```

### Exercise 4:

1. Create a `.gitignore` file in your repository:
   ```bash
   echo "*.tmp\nscratch/\n*.backup" > .gitignore
   ```
2. Add patterns to ignore:
   - All `.tmp` files
   - A directory called `scratch/`
   - All files ending in `.backup`
3. Create some test files matching these patterns:
   ```bash
   mkdir scratch
   echo "Temporary file." > temp.tmp
   echo "Backup file." > file.backup
   ```
4. Verify with `git status` that they are ignored:
   ```bash
   git status
   ```
5. Commit your `.gitignore` file:
   ```bash
   git add .gitignore
   git commit -m "Added .gitignore with ignore patterns"
   ```
