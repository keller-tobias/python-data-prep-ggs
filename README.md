# Preparations for Python course

Please follow the instructions below to set up your computer and the python environment.

# Setup Instructions

## 1. Git Setup

### 1.1 Install Git on your computer

- **Windows**: Download and install Git for Windows from [git-scm.com](https://git-scm.com/download/win).

- **Mac**: Follow the instructions on the [git-scm.com](https://git-scm.com/download/mac) website to install Git for Mac.

- **Linux** / **WSL (Windows Subsystem Linux)**: Use your package manager to install Git. For example, on Ubuntu, you can run:

```bash
sudo apt-get install git
```

### 1.2 Configure Git (only required once per machine and user)

Configure Git (in VS Code Terminal):

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

> 💡 **Tip:** If you want your initial branch to be named `main` instead of the default (`master` in older Git versions), you can add:
>
> ```bash
> git config --global init.defaultBranch main
> ```
>
> This ensures consistency with platforms like GitHub, which default to `main`.

Check your setup:

```bash
git config --list
```

### 1.3 GitHub Account Setup

1. Go to [https://github.com/](https://github.com/)
2. Click **Sign up**.
3. Enter a username, email, and password.
4. Verify your email address.
5. Choose the free plan (sufficient for this course).

You now have access to create and manage repositories on GitHub.

> **Tip**
> - You may want to setup a a **personal access** token in GitHub (if you're pushing to GitHub and prompted for credentials)
> - See [here] for more details: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token.

## 2. Install Git Large File Storage (git lfs)

To handle large files in Git, you need to install Git Large File Storage (git lfs). Follow the instructions below based on your operating system to be found on [https://git-lfs.com/](https://git-lfs.com/).

## 3. Setup VS Code

1. **Download and Install VS Code**:
   - Go to the [VS Code download page](https://code.visualstudio.com/download) and download the installer for your operating system.
   - Follow the installation instructions specific to your operating system.

2. **Install Python Extension for VS Code**:
   - Open VS Code.
   - Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X` (Windows) or `Cmd+Shift+X` (Mac).
   - Search for "Python" and install the official Python extension by Microsoft.

## 4. Initialize git lfs (only required once per machine and user)

Open a terminal (or PowerShell on Windows) and run the following command to clone the repository:

```bash
git lfs install
```

## 5. Clone the repository

Open a terminal (or PowerShell on Windows) and run the following command to clone the repository:

```bash
git clone https://github.com/keller-tobias/python-data-prep-ggs
```

If you have a slow internet connection the command above may hang. In that case, we can skip the large files in the first step and download them later. To do so, run the following command instead:

```bash
git -c filter.lfs.smudge= git clone https://github.com/keller-tobias/python-data-prep-ggs
```

## 6. Pull the large files

After cloning the repository, navigate into the project directory and pull the large files:

```bash
cd python-data-prep-ggs
git lfs pull
```

## 7. Setting up the python environment

### Installation on Windows

#### 1. Install the python package manager `uv`

Open a PowerShell terminal (just search for "PowerShell" in the Start menu), then enter

```powershell
# using the uv installer script
powershell -ExecutionPolicy Bypass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Alternatively, if you have winget installed, you can run the following command:

```powershell
# alternatively, using winget
winget install --id=astral-sh.uv  -e
```

If you see a PATH warning for `C:\Users\<you>\.local\bin`, let `uv` update your shell configuration:

```powershell
uv tool update-shell
```

Or update the PATH for the session:

```powershell
$env:Path = "$env:USERPROFILE\.local\bin;$env:Path"
```

#### 2. Setup a virtual environment for the project

Open the Powershell, then:

##### 1. Navigate to the repository directory.

```powershell
cd path\to\python-data-prep-ggs
```

##### 2. You can check if the directory is correct: the following command should list the files in the project directory, particulalry "pyproject.toml" and the subfolder "notebooks".

```powershell
ls
```

##### 3. Create a new virtual environment with python 3.13 (will be downloaded automatically if not installed).

```powershell
# this will create a new virtual environment inside the project folder (named ".venv")
uv venv --python=3.13
```

##### 4. Activate the virtual environment.

```powershell
.\.venv\Scripts\Activate.ps1
```

If activation fails with a scripts-disabled error, set the execution policy for **this session only** and retry activation:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\.venv\Scripts\Activate.ps1
```

(For a persistent setting per user, use `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`.)

##### 5. Install the project dependencies.

```powershell
uv sync
```

### Installation on MacOS

#### 1. Install the python package manager `uv`

Run the following command in the terminal:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

If your system doesn't have curl, you can use wget:

```bash
wget -qO- https://astral.sh/uv/install.sh | sh
```

#### 2. Setup a virtual environment for the project

Open the terminal, then:

##### 1. Navigate to the project directory.

```bash
cd path/to/python-data-prep-ggs
```

##### 2. Check if the directory is correct

The following command should list the files in the project directory, particulalry "pyproject.toml" and the subfolder "notebooks".

```bash
ls
```

##### 3. Create a new virtual environment with python 3.13 (will be downloaded automatically if not installed).

```bash
uv venv --python=3.13
```

##### 4. Activate the virtual environment.

```bash
source .venv/bin/activate
```

##### 5. Install the project dependencies.

```bash
uv sync
```