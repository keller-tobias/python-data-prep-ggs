# Preparations for Python course

Please follow the instructions below to set up your computer and the python environment.

# 1. Optimizing your workspace for remote course attendance

## 🖥️ Use a second monitor

It may be helpful to work with a second monitor so that you can watch the instructions while working on your main screen.

## 🤝 Meet up with other participants

If you have a meeting room with projector capabilities, consider meeting up with other participants to follow along with the instructions together.

## 📷 Turn on your camera:

The course is intended to be as interactive as possible. Please turn on your camera during the sessions to enhance engagement and collaboration.

# 2. Required software for the Python course and setup instructions

We require the following software to be installed on your computer:

   - [VS Code](https://code.visualstudio.com/) (with Python and Jupyter extensions)
   - [Git](https://git-scm.com/)
   - [GitHub account](https://github.com/)
   - [`uv` Python environment manager](https://astral.sh/uv/)
   - Further instructions for setting up the python environment are provided during the course.

Please follow the instructions below to install the required software on your computer. The specific steps may differ between operating systems.

## 2.1. Setup VS Code

### Download and Install VS Code
   - Go to the [VS Code download page](https://code.visualstudio.com/download) and download the installer for your operating system.
   - Follow the installation instructions specific to your operating system.

### Install Python and Jupyter Extensions for VS Code
   - Open VS Code.
   - Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X` (Windows) or `Cmd+Shift+X` (Mac).
   - Search for "Python" and install the official Python extensions by Microsoft.
   - Similarly, install the "Jupyter" extension by Microsoft.

### Install additional, useful extensions
   - "Data Wrangler" (Microsoft) - search for: `ms-toolsai.datawrangler`
   - "Github Copilot" (GitHub) - search for: `github.copilot`
   - "Github Copilot Chat" (GitHub) - search for: `github.copilot-chat`
   - "Git Graph" (mhutchie) - search for: `mhutchie.git-graph`
   - "Ruff" (Astral Software) - search for: `charliermarsh.ruff`


## 2.2. Git Setup

### Install Git on your computer

- **Windows**: Download and install Git for Windows from [git-scm.com](https://git-scm.com/download/win).

- **Mac**: Follow the instructions on the [git-scm.com](https://git-scm.com/download/mac) website to install Git for Mac.

- **Linux** / **WSL (Windows Subsystem Linux)**: Use your package manager to install Git. For example, on Ubuntu, you can run:

```bash
sudo apt-get install git
```

### Configure Git (only required once per machine and user)

Configure Git (in system terminal / PowerShell / git bash, or VS Code Terminal):

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

## 2.3 GitHub Account Setup

1. Go to [https://github.com/](https://github.com/)
2. Click **Sign up**.
3. Enter a username, email, and password.
4. Verify your email address.
5. Choose the free plan (sufficient for this course).
6. Apply for an education account (if you have a .edu email address): navigate to the [GitHub Education](https://education.github.com/) page and follow the instructions. This will allow you to access additional benefits, such as a free GitHub Copilot subscription.

You now have access to create and manage repositories on GitHub.

> **Tip**
> - You may want to setup a a **personal access** token in GitHub (if you're pushing to GitHub and prompted for credentials)
> - See [https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) for more details.

## 2.4. Install `uv`

This section gives the minimal, standalone steps to install the `uv` Python environment manager on your machine.

### Windows

The instructions for installing Windows depend on whether you have **administrative rights** on your machine.

Select the appropriate instruction manual from below:

- Option A: [with **administrative rights**](setup-uv-windows-admin.md) or the pdf ([setup-uv-windows-admin.pdf](setup-uv-windows-admin.pdf))
- Option B: [without **administrative rights**](setup-uv-windows-no-admin.md) or the pdf ([setup-uv-windows-no-admin.pdf](setup-uv-windows-no-admin.pdf))

### macOS / Linux / WSL

- Install using the shell installer (works with `curl` or `wget`):

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
# or, if you prefer wget:
# wget -qO- https://astral.sh/uv/install.sh | sh
```

- After installation, ensure `~/.local/bin` is on your `PATH` (the installer can update your shell):

```bash
export PATH="$HOME/.local/bin:$PATH"
# Add the line above to ~/.bashrc, ~/.profile, or ~/.zshrc to persist.
```

- Open a new terminal session. Then:

```bash
uv --version
```

If the command prints a version, the installation succeeded.
