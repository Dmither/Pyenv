# PYENV environments
## On linux
### Install

```bash
$ sudo get-apt update
$ sudo get-apt upgrade
$ curl https://pyenv.run | bash
$ echo 'export PATH="$HOME/.pyenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc
# if doesn't add python version:
$ sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev
```

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
