## Requirements

To get this repo up and running, you will need to ensure your system is setup with the following:

1. [pyenv-win](https://github.com/pyenv-win/pyenv-win) for managing installations of pythons on Windows
   - Python 3.9.13 needs to be installed through pyenv.
2. [Poetry](https://python-poetry.org/) for project based package dependency of our codebase.

See this [PowerShell script](https://github.com/SethDocherty/dev.env/blob/main/Python/Installing%20Python/Install_python_development_env.ps1) to automate the installation of pyenv-win and Poetry.

## Setting up the Repo Environment

Before installing the project through poetry, let's do a quick check to ensure we can install the project python dependencies. If you know you're up to date, feel free to skip this section.

1. Open Command Prompt (CMD) or PowerShell and check the following:
   - Check if python 3.9.13 has been set to your global interrupter through pyenv. You can identify this by running the command `pyenv global` to return what it is currently set to.
2. Run the command `poetry about` to see which version have. If it is below 1.3.0, run the following command:

   `(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python - --uninstall`

   - After uninstalling, run the same command above without the `--uninstall` flag

   3. To ensure that that the virtual environment is [installed to the root of the project directory](https://python-poetry.org/docs/configuration/#virtualenvsin-project), run the following command:
      `poetry config virtualenvs.in-project true`

### Now, to set-up the repo environment start by:

1. Open Command Prompt (CMD) or PowerShell to the project repo root folder.
2. Run the command `poetry install`. _NOTE: this may take some time to run_. After it's finished you should see the directory .venv in the root of the project folder.
   - _NOTE: For Linux based machines run `source .venv/bin/activate` to activate the virtual environment. For Windows, run `.venv\Scripts\activate` to activate the environment._
