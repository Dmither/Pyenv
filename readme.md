# PYENV environments

## On Windows
### Install

The easiest way to install pyenv-win is to run the following installation command in a PowerShell terminal:

```pwsh
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```

If **UnauthorizedAccess**  run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine`.

```pwsh
[System.Environment]::SetEnvironmentVariable('PYENV',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('PYENV_ROOT',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('PYENV_HOME',$env:USERPROFILE + "\.pyenv\pyenv-win\","User")
[System.Environment]::SetEnvironmentVariable('path', $env:USERPROFILE + "\.pyenv\pyenv-win\bin;" + $env:USERPROFILE + "\.pyenv\pyenv-win\shims;" + [System.Environment]::GetEnvironmentVariable('path', "User"),"User")
```

### Commands

```yml
   commands     List all available pyenv commands
   local        Set or show the local application-specific Python version
   global       Set or show the global Python version
   shell        Set or show the shell-specific Python version
   install      Install 1 or more versions of Python 
   uninstall    Uninstall 1 or more versions of Python
   update       Update the cached version DB
   rehash       Rehash pyenv shims (run this after switching Python versions)
   vname        Show the current Python version
   version      Show the current Python version and its origin
   version-name Show the current Python version
   versions     List all Python versions available to pyenv
   exec         Runs an executable by first preparing PATH so that the selected Python
   which        Display the full path to an executable
   whence       List all Python versions that contain the given executable
```

## On linux
### Install

```bash
$ sudo apt-get update
$ sudo apt-get upgrade
$ curl https://pyenv.run | bash
$ echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
# if doesn't add python version:
$ sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

!!!! After installation restart terminal !!!!

### Commands

Each command has a --help flag

`$ pyenv commands` show all pyenv commands  
`$ pyenv version` show python active version  
`$ pyenv versions` show all versions and *active

`$ pyenv install [ver]` install python version (3.11.0)  
`-l`, `--list` show all available for instalation  
`$ pyenv uninstall [ver]` uninstall python version

`$ pyenv global [ver]` switch to python version (global)  
`$ pyenv global system` switch to system version (global)  
`$ pyenv local [ver]` switch to version (local, for proj)  
`$ pyenv shell [ver]` switch to version (for shell)

`$ pyenv virtualenv [ver] [name]` create virtualenv  
`$ pyenv virtualenv-delete [name]` delete virtualenv
`$ pyenv local [envname]` activate environment  
`$ pyenv activate [envname]` activate by hands  
`$ pyenv deactivate` deactivate active by hands


`$ which [file]` show full path to executable system file  
`$ rm -rf ~/.pyenv/versions/[ver]` remove version dir  
`$ ls ~/.pyenv/versions/` show versions directiories  
`$ python -m test` test active python version  
