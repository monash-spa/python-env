# Monash SPA Python Environment

Welcome! This guide will help you set up the Python environment you'll need for your Honours coursework. Don't worry if you're new to programming or using the command line – we'll walk through everything step by step.

## What You'll Install

This environment includes essential tools for astronomy and physics research:
- **Astropy** and related tools for astronomical data analysis
- **NumPy** and **SciPy** for numerical computing
- **Pandas** for data manipulation
- **Jupyter** notebooks for interactive analysis
- And several other specialized astronomy packages

## Table of Contents

- [Installation](#installation)
   - [macOS](#macos-setup-instructions)
   - [Linux](#linux-setup-instructions)
   - [Windows](#windows-setup-instructions)
- [Verifying Your Installation](#verifying-your-installation)
- [Using the Environment](#using-the-environment)
- [Troubleshooting](#troubleshooting)

---

## Installation

### macOS Setup Instructions

#### Step 1: Open the Terminal

The Terminal is an application that lets you type commands to control your computer.

1. Press `Command (⌘) + Space` to open Spotlight Search
2. Type "Terminal" and press Enter
3. A window with white or black background will appear – this is your terminal

#### Step 2: Install uv (the Python package manager)

Copy and paste this command into your terminal and press Enter:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**What this does:** Downloads and installs `uv`, a fast Python package manager that will help manage your Python environment.

After installation completes, close and reopen your Terminal window for the changes to take effect.

#### Step 3: Verify uv is installed

Type this command and press Enter:

```bash
uv --version
```

You should see a version number (like `0.5.0` or similar). If you see an error, try closing and reopening Terminal again.

#### Step 4: Download this repository

You need to download this project to your computer. There are two ways to do this:

**Option A: Using git (if you've used it before)**

```bash
cd ~
git clone https://github.com/monash-spa/python-env.git honours-env
cd honours-env
```

**Option B: Download as ZIP (if you haven't used git)**

1. Go to the repository page: https://github.com/monash-spa/python-env
2. Click the green "Code" button
3. Click "Download ZIP"
4. Once downloaded, double-click the ZIP file to extract it
5. Rename the extracted folder to `honours-env`
6. Move the `honours-env` folder to your home folder (the folder with your username)
7. In Terminal, navigate to it:

```bash
cd ~/honours-env
```

**Tip:** You can drag and drop the `honours-env` folder from Finder into Terminal after typing `cd ` (with a space) to automatically fill in the path.

Verify you're in the right place by running:

```bash
ls
```

You should see files including `pyproject.toml` and `README.md`.

#### Step 5: Create and activate the Python environment

Run this command:

```bash
uv sync
```

**What this does:** Creates a virtual Python environment and installs all the required packages listed in `pyproject.toml`. This might take a few minutes the first time.

#### Step 6: Start using Python

To run Python with all the installed packages:

```bash
uv run python
```

To start a Jupyter notebook:

```bash
uv run jupyter notebook
```

---

### Linux Setup Instructions

#### Step 1: Open the Terminal

The method varies by Linux distribution:

- **Ubuntu/Debian**: Press `Ctrl + Alt + T`
- **Or** search for "Terminal" in your applications menu
- A window will appear where you can type commands

#### Step 2: Install uv (the Python package manager)

Copy and paste this command into your terminal and press Enter:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**What this does:** Downloads and installs `uv`, a fast Python package manager.

After installation completes, either close and reopen your Terminal, or run:

```bash
source $HOME/.cargo/env
```

#### Step 3: Verify uv is installed

Type this command and press Enter:

```bash
uv --version
```

You should see a version number. If you get a "command not found" error, make sure you reopened your terminal or ran the source command above.

#### Step 4: Download this repository

You need to download this project to your computer. There are two ways to do this:

**Option A: Using git (if you've used it before)**

```bash
cd ~
git clone https://github.com/monash-spa/python-env.git honours-env
cd honours-env
```

**Option B: Download as ZIP (if you haven't used git)**

1. Go to the repository page: https://github.com/monash-spa/python-env
2. Click the green "Code" button
3. Click "Download ZIP"
4. Once downloaded, extract the ZIP file (usually you can right-click it and select "Extract Here")
5. Rename the extracted folder to `honours-env`
6. Move the `honours-env` folder to your home folder
7. In Terminal, navigate to it:

```bash
cd ~/honours-env
```

Verify you're in the right place by running:

```bash
ls
```

You should see files including `pyproject.toml` and `README.md`.

#### Step 5: Create and activate the Python environment

Run this command:

```bash
uv sync
```

**What this does:** Creates a virtual Python environment and installs all required packages. This will take a few minutes the first time.

**Note:** Some packages may require system libraries. If you encounter errors, you might need to install build dependencies:

```bash
# For Ubuntu/Debian:
sudo apt-get update
sudo apt-get install -y python3-dev build-essential

# For Fedora:
sudo dnf install python3-devel gcc gcc-c++
```

#### Step 6: Start using Python

To run Python with all the installed packages:

```bash
uv run python
```

To start a Jupyter notebook:

```bash
uv run jupyter notebook
```

---

### Windows Setup Instructions

#### Step 1: Open PowerShell

PowerShell is Windows' command-line interface (similar to Terminal on Mac/Linux).

**Method 1:**
1. Press `Windows Key + X`
2. Click "Windows PowerShell" or "Terminal"

**Method 2:**
1. Press `Windows Key`
2. Type "PowerShell"
3. Click "Windows PowerShell"

#### Step 2: Install uv (the Python package manager)

Copy and paste this command into PowerShell and press Enter:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**What this does:** Downloads and installs `uv`, a fast Python package manager.

**Important:** After installation, close PowerShell completely and open a new PowerShell window.

#### Step 3: Verify uv is installed

Type this command and press Enter:

```powershell
uv --version
```

You should see a version number (like `0.5.0` or similar).

**If you see an error about execution policy:**
Run PowerShell as Administrator (right-click PowerShell and select "Run as administrator"), then run:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

#### Step 4: Download this repository

You need to download this project to your computer. There are two ways to do this:

**Option A: Using git (if you've used it before)**

```powershell
cd ~
git clone https://github.com/monash-spa/python-env.git honours-env
cd honours-env
```

**Option B: Download as ZIP (if you haven't used git)**

1. Go to the repository page: https://github.com/monash-spa/python-env
2. Click the green "Code" button
3. Click "Download ZIP"
4. Once downloaded, right-click the ZIP file and select "Extract All..."
5. Extract it to your user folder (usually `C:\Users\YourUsername\`)
6. Rename the extracted folder to `honours-env`
7. In PowerShell, navigate to it:

```powershell
cd ~\honours-env
```

**Tip:** You can drag and drop the `honours-env` folder into PowerShell after typing `cd ` (with a space) to automatically fill in the path.

Verify you're in the right place by running:

```powershell
Get-ChildItem
```

You should see files including `pyproject.toml` and `README.md`.

#### Step 5: Create and activate the Python environment

Run this command:

```powershell
uv sync
```

**What this does:** Creates a virtual Python environment and installs all required packages. This will take several minutes the first time.

#### Step 6: Start using Python

To run Python with all the installed packages:

```powershell
uv run python
```

To start a Jupyter notebook:

```powershell
uv run jupyter notebook
```

---

## Verifying Your Installation

After completing the setup for your operating system, let's verify everything works correctly.

### Test Python import

Run Python:

```bash
uv run python
```

In the Python prompt that appears (looks like `>>>`), try importing the main packages:

```python
import numpy
import astropy
import pandas
print("Success! All packages imported correctly.")
```

Type `exit()` or press `Ctrl+D` (macOS/Linux) or `Ctrl+Z` then Enter (Windows) to leave Python.

### Test Jupyter

Start Jupyter:

```bash
uv run jupyter notebook
```

Your web browser should open with the Jupyter interface. You can create a new notebook and test importing packages there too.

To stop Jupyter, go back to your terminal/PowerShell and press `Ctrl+C`, then type `y` and press Enter.

---

## Using the Environment

### Every time you want to work on your project:

1. Open your terminal/PowerShell
2. Navigate to the honours-env folder:
   ```bash
   cd ~/honours-env
   ```
3. Run Python or Jupyter with:
   ```bash
   uv run python
   # or
   uv run jupyter notebook
   ```

### Running Python scripts

If you have a Python script (e.g., `my_analysis.py`), run it with:

```bash
uv run python my_analysis.py
```

### Adding new packages

If your supervisor asks you to install additional packages, you can add them:

```bash
uv add package-name
```

For example:
```bash
uv add matplotlib
```

---

## Troubleshooting

### "uv: command not found" or "uv is not recognized"

**Solution:** Close and reopen your terminal/PowerShell completely. The uv installation needs a fresh terminal session to work.

### "Permission denied" errors (macOS/Linux)

**Solution:** Don't use `sudo` with uv commands. If you see permission errors, check that you own the project folder:

```bash
ls -la
```

### Jupyter doesn't open in my browser

**Solution:** Look for a URL in the terminal output that looks like `http://localhost:8888/?token=...`. Copy this entire URL and paste it into your web browser.

### Slow installation

**Solution:** Some packages (especially `corrfunc`) need to be compiled, which takes time. This is normal. Grab a coffee and wait for it to complete.

### "ImportError" when running Python

**Solution:** Make sure you're running Python with `uv run python`, not just `python`. The `uv run` part is what activates your environment with all the installed packages.

### Still having problems?

[Create a GitHub issue](github.com/monash-spa/python-env/issues/new) that describes the problem in detail, including:
1. Your operating system (macOS, Linux, or Windows)
2. The exact error message you're seeing
3. The thing you were trying to do

---

## Additional Resources

- **uv Documentation**: https://docs.astral.sh/uv/
- **Astropy Tutorials**: https://learn.astropy.org/
- **Jupyter Documentation**: https://jupyter-notebook.readthedocs.io/

---

Good luck with your honours year! 🔭✨
