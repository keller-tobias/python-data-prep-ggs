# Git Intro: Basic Workflow, Branching, and .gitignore

# 1. Basic Git Workflow

> 💡 **Tip (Reminder):** If you want your initial branch to be named `main` instead of the default (`master` in older Git versions), you can add:
>
> ```bash
> git config --global init.defaultBranch main
> ```
>
> This ensures consistency with platforms like GitHub, which default to `main`.


## 1.1 Initialize a Repository

Here, we create a new local Git repository and make our first commit.

1. Open a new folder in VS Code.
2. Open the terminal.
3. Initialize the Git repository:

```bash
git init
```

4. Create a new file `hello.txt` with some text.
5. Check the status:

```bash
git status
```

6. Stage the file:

```bash
git add hello.txt
```

7. Commit the file:

```bash
git commit -m "Initial commit with hello.txt"
```

## 1.2 Making and Tracking Changes

Here, we learn how to make changes and view the history.

### Tutorial:

1. Edit `hello.txt` by adding another line.
2. Check what's changed:

    ```bash
    git status
    git diff
    ```

3. Stage and commit again:

    ```bash
    git add hello.txt
    git commit -m "Updated hello.txt"
    ```

4. View commit history:

    ```bash
    git log --oneline
    ```

### Exercise 1:

1. Create a new file `second_file.txt` with some text.
2. Stage this new file.
3. Commit it with a message.
4. Modify `second_file.txt` and stage the changes.
5. Modify `hello.txt` again and stage the changes.
6. Commit both changes together with a single commit message.

## 1.3 Undoing Changes

### Tutorial:

1. Modify `hello.txt` and stage the changes.


2. Unstage the changes:

This is harmless because the changes are still in the working directory:

```bash
git restore --staged hello.txt
```


3. Discard changes in `hello.txt`:

This will remove the changes made to the file since the last commit. Since this will delete all uncommited changes to the specified file, use it with caution:

```bash
git restore hello.txt
```

> **IMPORTANT**: if you do not list specific files after `git restore`, the command will discard all changes in the working directory!


4. If you want to undo the last commit but keep the originally commited changes in the stage area, use the `--soft` option.

Both unstaged and staged changes will be kept in this case, in addition to the changes that were originally commited:

```bash
git reset --soft HEAD~1
```

> **NOTE**: `HEAD~1` refers to the last commit. You can also use `HEAD^` or `HEAD~2` to refer to earlier commits. Or you can use the commit hash directly, e.g. `git reset --soft 1234567`. The hash can be found in the output of `git log --oneline`.

5. If you want to undo the last commit and discard all changes, use the `--hard` option. Use this with caution, as it will delete all changes made in the last commit

```bash 
git reset --hard HEAD~1
```

>**NOTE**: This will delete all changes made in the last commit, including staged and unstaged changes. Use this command **with caution**!


### Exercise 2:

1. Modify `second_file.txt` and stage the changes.
2. Unstage the changes.
3. Discard the changes in `second_file.txt`.
4. Modify `second_file.txt` again
5. Add a new file `third_file.txt` with some text.
6. Stage both files.
7. Commit both files together with a message.
8. Make a change to `third_file.txt` and stage the changes.
9. Undo the last commit using `--soft` and check the status.
10. Undo the last commit using `--hard` and check the status.


## 2. Branching

### 2.1 What Are Branches?

Branches in Git are a way to work on different versions of a project simultaneously. They allow you to isolate changes, experiment with new features, or fix bugs without affecting the main codebase. The `main` branch is typically the default branch where the stable version of the code resides.

### 2.2 Why Use Branches?

- **Isolation**: Keep experimental or incomplete work separate from the main codebase.
- **Collaboration**: Multiple team members can work on different features or fixes simultaneously.
- **Version Control**: Easily switch between different versions of the project.

### 2.3 Best Practices for Branch Naming

1. Use descriptive names that clearly indicate the purpose of the branch.
   - Example: `feature/login-page`, `bugfix/header-alignment`, `hotfix/security-patch`
2. Use prefixes to categorize branches:
   - `feature/` for new features
   - `bugfix/` for bug fixes
   - `hotfix/` for urgent fixes
3. Avoid using spaces or special characters in branch names. Use hyphens (`-`) or slashes (`/`) instead.
4. Keep branch names short but meaningful.

### 2.4 Creating and Merging Branches

#### Tutorial:

1. Create and switch to a new branch:

    ```bash
    git switch -c feature-1
    ```

2. Modify `hello.txt` (add a new line).
3. Stage and commit:

    ```bash
    git add hello.txt
    git commit -m "first changes for feature-1"
    ```

4. Switch back to `main`:

    ```bash
    git switch main
    ```

5. Merge the branch:

    ```bash
    git merge feature-1
    ```

6. To view the commit history of the current branch, use:

    ```bash
    git log --oneline --graph
    ```

7. Delete the `feature-1` branch after merging (optional):

    ```bash
    git branch -d feature-1
    ```

#### Exercise 3:

1. Create a new branch called `feature-2`.
2. Add a new file `feature2.txt` with some text.
3. Stage and commit the new file.
4. Switch back to the `main` branch.
5. Modify `hello.txt` by adding another line and commit the changes.
6. Merge the `feature-2` branch into `main`.
7. Resolve any merge conflicts if they occur.
8. View the commit history to verify the merge.

### 2.5 Resolving Merge Conflicts

When merging branches, you may encounter conflicts if changes in the branches overlap. For a detailed guide on resolving merge conflicts, see section 3.5 in the [Collaboration guide](02-collaboration.md).

## 3. Managing Files with .gitignore

Not all files in your project should be tracked by Git. Some files are temporary, generated automatically, or contain sensitive information.

### 3.1 What is .gitignore?

The `.gitignore` file tells Git which files and directories to ignore and never track. This file should be placed in your repository root.

### 3.2 Common Files to Ignore

#### Tutorial:

1. **Create a .gitignore file** in your repository root:

```bash
# In VS Code, create a new file called .gitignore
```

2. **Add common ignore patterns**:

```
# Operating system files
.DS_Store
Thumbs.db

# Editor files
.vscode/settings.json
*.swp
*.tmp

# Temporary files
temp/
*.log

# Dependencies (for programming projects)
node_modules/
__pycache__/
*.pyc
```

3. **Test the .gitignore**:
   - Create a file called `temp.log`
   - Run `git status` - the file should not appear in untracked files
   - If it does appear, check your .gitignore syntax

> 💡 **Tip**: Use [gitignore.io](https://gitignore.io) to generate .gitignore files for specific programming languages and tools.

### 3.3 Important .gitignore Rules

1. **Patterns are relative** to the .gitignore file location
2. **Use `*` for wildcards**: `*.log` ignores all .log files
3. **Use `/` for directories**: `temp/` ignores the temp directory
4. **Use `!` to negate**: `!important.log` tracks this file even if `*.log` is ignored
5. **Comments start with `#`**

#### Exercise 4:

1. Create a `.gitignore` file in your repository.
2. Add patterns to ignore:
   - All `.tmp` files
   - A directory called `scratch/`
   - All files ending in `.backup`
3. Create some test files matching these patterns.
4. Verify with `git status` that they are ignored.
5. Commit your `.gitignore` file.

> ⚠️ **Important**: If a file is already tracked by Git, adding it to .gitignore won't stop tracking it. You need to untrack it first with `git rm --cached <file>`.
