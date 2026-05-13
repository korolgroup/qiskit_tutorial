# Python venv Cheatsheet

## Create Virtual Environment
```bash
# Creates isolated Python environment named .venv
python -m venv .venv
```
*On some systems use `python3 -m venv .venv`*

## Activate Environment

### macOS/Linux
```bash
# Activates the virtual environment (changes your shell prompt)
source .venv/bin/activate
```

### Windows (PowerShell)
```bash
# Activates venv in PowerShell (may need Set-ExecutionPolicy first)
.venv\Scripts\Activate.ps1
```

### Windows (CMD)
```bash
# Activates venv in Command Prompt
.venv\Scripts\activate.bat
```

## Verify Environment is Active
```bash
# Shows Python path inside venv (not system Python)
which python
# or
python --version    # Shows venv Python version
pip --version       # Shows pip from venv
```

## Install Packages
```bash
# Installs package only in this venv (not system-wide)
pip install numpy

# Install multiple packages
pip install numpy pandas matplotlib
```

## Upgrade pip
```bash
# Updates pip to latest version within venv
python -m pip install --upgrade pip
```

## List Installed Packages
```bash
# Shows all packages + versions in this venv
pip list
```

## Save Dependencies
```bash
# Exports exact package list/versions to requirements.txt
pip freeze > requirements.txt
```

## Install from Requirements
```bash
# Installs all packages from requirements.txt file
pip install -r requirements.txt
```

## Deactivate Environment
```bash
# Returns to system Python (simple one-word command)
deactivate
```

## Delete Environment
```bash
# Simply delete the folder (venv gone forever)
rm -rf .venv          # macOS/Linux
rmdir /s /q .venv     # Windows CMD
```

## Best Practices

* Name it .venv (standard convention)
* Add .venv/ to .gitignore
* Always use python -m pip (safer)
* Recreate venv if dependencies break
* Don't commit venv folder to git


## Complete Workflow Example
```bash
python -m venv .venv                    # Create
source .venv/bin/activate              # Activate  
python -m pip install --upgrade pip    # Update pip
pip install -r requirements.txt        # Install deps
python main.py                         # Run code
deactivate                             # Exit
```
