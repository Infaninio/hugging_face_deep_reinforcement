# hugging_face_deep_reinforcement

## Project Setup

### Virtual Environment
The virtual environment can be created with 'venv', 'virtualenv' or equivalent.
Conda must not be used to create the virtual environment.

To handle different python versions [pyenv](https://github.com/pyenv/pyenv) is a good tool which allows to set 
different python versions for different folders.
Change the extra-index-url according to your hardware (gpu) and the installed cuda version. See [PyTorch GetStarted](https://pytorch.org/get-started/locally/)

To install the necessary packages run:
```shell
pip install pip-tools
pip-sync requirements.txt --extra-index-url https://download.pytorch.org/whl/cu116
```

### OS-Dependencies
```shell
sudo apt-get install python-opengl ffmpeg xvfb
```

## Development

### Change project requirements
To create and/or update the requirements change the necessary package list in either the [pyproject.toml](./pyproject.toml).
The [pyproject.toml](./pyproject.toml) contains all packages which are necessary base dependencies.

For generating the *.txt files containining the packages with the pinned version install
piptools and run pip-compile.

```shell
pip-compile pyproject.toml >> requirements.txt
```