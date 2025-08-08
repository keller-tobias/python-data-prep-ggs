# Collaboration with Remote Repositories

Remote repositories allow you to collaborate with others and back up your work online. GitHub is the most popular platform for hosting Git repositories.

## 1. Working with GitHub

### 1.1 Creating a Remote Repository

#### Tutorial:

1. Log in to GitHub and click the **+** icon in the top-right corner.
2. Select **New repository**.
3. Enter a repository name (e.g., `git-practice`).
4. Choose Public or Private visibility.
5. **Important**: Do NOT initialize with README, .gitignore, or license if you already have a local repository.
6. Click **Create repository**.

> 💡 **Tip**: If you're starting fresh, you can initialize with a README and then clone the repository locally instead.

### 1.2 Connecting Local to Remote

#### Tutorial:

1. Copy the repository URL from GitHub (choose HTTPS for simplicity).
2. In your local repository, link it to the remote:

```bash
git remote add origin https://github.com/your-username/git-practice.git
```

3. Verify the remote connection:

```bash
git remote -v
```

You should see output showing both fetch and push URLs.

> **Important**: The name `origin` is a convention for the main remote repository. You can use other names, but `origin` is standard.

### 1.3 Pushing to GitHub

#### Tutorial:

1. Push your code to GitHub for the first time:

```bash
git push -u origin main
```

2. Refresh your GitHub page to see your files online.

> 💡 **Explanation**: The `-u` flag sets up tracking between your local `main` branch and the remote `main` branch. After this, you can use just `git push` for future pushes.

#### Exercise 1:

1. Create a new repository on GitHub called `git-exercise`.
2. Connect your local repository to this new remote.
3. Push all your existing commits to GitHub.
4. Verify that all your files and commit history appear on GitHub.

## 2. Synchronizing Changes

### 2.1 Making and Pushing Local Changes

#### Tutorial:

1. Make local changes to an existing file:

```bash
# Edit hello.txt (add a new line)
```

2. Stage and commit the changes:

```bash
git add hello.txt
git commit -m "Updated hello.txt for remote demo"
```

3. Push the changes to GitHub:

```bash
git push
```

4. Check GitHub to see your new commit.

### 2.2 Pulling Remote Changes

Sometimes others (or you from another computer) make changes to the remote repository. You need to pull these changes locally.

#### Tutorial:

1. Make a change directly on GitHub:
   - Navigate to one of your files on GitHub
   - Click the pencil icon to edit
   - Make a small change and commit it through the web interface

2. Back in your local repository, pull the changes:

```bash
git pull
```

3. Check that the remote changes are now in your local files.

> **Important**: Always pull before starting new work, especially when collaborating with others.

#### Exercise 2:

1. Edit a file directly on GitHub through the web interface.
2. Make another local change to a different file.
3. Try to push your local changes (this should fail).
4. Pull the remote changes first, then push your local changes.
5. Verify both changes are present locally and remotely.

## 3. Understanding Fetch vs Pull

### 3.1 Git Fetch

`git fetch` downloads changes from the remote but doesn't merge them into your current branch:

```bash
git fetch
```

This is useful when you want to see what changes exist remotely before merging them.

### 3.2 Git Pull

`git pull` will fetch and then merge the changes into your current branch:

```bash
git pull
```

> 💡 **Best Practice**: Use `git fetch` first to see what changes exist, then `git pull` to merge them.

## 4. Topics out of Scope

This section covers the basics of working with remote repositories. For more advanced topics like handling merge and push conflicts, pull requests, forking, and GitHub Actions, refer to the [Resources and Best Practices](04-resources.md) section.