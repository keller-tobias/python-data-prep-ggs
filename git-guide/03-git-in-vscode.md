# Using Git in VS Code

VS Code provides excellent built-in Git integration, making version control more visual and intuitive. You can perform most Git operations without leaving the editor.

## 1. Source Control Panel

### 1.1 Opening the Source Control Panel

#### Tutorial:

1. Click the Source Control icon in the left sidebar (looks like a branching diagram).
2. The panel shows:
   - **Changes**: Modified files that haven't been staged
   - **Staged Changes**: Files ready to be committed
   - **Merge Changes**: Files with conflicts (if any)

> 💡 **Tip**: The number badge on the Source Control icon shows how many files have changes.

### 1.2 Understanding File Status Icons

In the Source Control panel and Explorer, you'll see different symbols:
- **U**: Untracked (new file)
- **M**: Modified
- **A**: Added (staged)
- **D**: Deleted
- **R**: Renamed
- **C**: Copied

## 2. Basic Git Operations in VS Code

### 2.1 Staging and Committing

#### Tutorial:

1. **Stage individual files**:
   - Click the `+` icon next to a file to stage it
   - Or hover over "Changes" and click `+` to stage all files

2. **Unstage files**:
   - Click the `-` icon next to a staged file

3. **Commit changes**:
   - Type a commit message in the input box at the top
   - Click the checkmark (✓) to commit
   - Or use `Ctrl + Enter` (Windows/Linux) or `Cmd + Enter` (Mac)

4. **View changes**:
   - Click on a modified file to see a side-by-side diff
   - Green highlights show additions
   - Red highlights show deletions

> 💡 **Tip**: You can also stage specific lines by opening a file's diff view and clicking the `+` icon next to individual changes.

#### Exercise 1:

1. Make changes to multiple files in your project.
2. Use the Source Control panel to stage only some of the files.
3. Commit the staged files with a descriptive message.
4. Stage and commit the remaining files separately.
5. Compare how this differs from using command line Git.

### 2.2 Viewing Git History

#### Tutorial:

1. **Timeline view**:
   - Open a file and look at the Timeline panel at the bottom of the Explorer
   - This shows the commit history for the current file

2. **Git Graph** (if extension is installed):
   - Open Command Palette (`Ctrl + Shift + P`)
   - Type "Git Graph" and select "Git Graph: View Git Graph"

## 3. Branch Management in VS Code

### Tutorial:

1. **View current branch**:
   - Look at the bottom-left corner of VS Code
   - The current branch name is displayed there

2. **Create a new branch**:
   - Click the branch name in the bottom-left corner
   - Select "Create new branch..." 
   - Enter a branch name and press Enter

3. **Switch branches**:
   - Click the branch name in the bottom-left corner
   - Select from the list of available branches

4. **Merge branches**:
   - Use the "..." menu in the Source Control panel
   - Select "Branch" → "Merge Branch..."
   - Choose the branch to merge

> 💡 **Alternative**: You can also use the Command Palette (`Ctrl + Shift + P`) and search for "Git" to see all available Git commands.

### Exercise 2:

1. Create a new branch called `vscode-practice` using the VS Code interface.
2. Make some changes and commit them.
3. Switch back to the main branch.
4. Notice how VS Code automatically updates your files when switching branches.
5. Merge the `vscode-practice` branch back into main.

## 4. Remote Operations

### Tutorial:

1. **Sync (Push + Pull)**:
   - Click the circular arrows icon in the bottom-left corner
   - This performs both pull and push operations

2. **Manual Push/Pull**:
   - Click the "..." menu in the Source Control panel
   - Select "Push" or "Pull"

3. **View remote status**:
   - The status bar shows if you're ahead/behind the remote
   - Example: "↑2 ↓1" means 2 commits ahead, 1 commit behind

> ⚠️ **Warning**: Always check what changes you're pushing/pulling, especially when collaborating with others.

### Exercise 3:

1. Make a local change and commit it.
2. Use VS Code to push the change to your remote repository.
3. Make a change directly on GitHub.
4. Use VS Code to pull the remote change.
5. Observe how VS Code shows the sync status in the bottom bar.
