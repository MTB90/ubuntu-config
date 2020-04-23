## Instruction for setup pyenv and pipenv 

1) Installation pyenv
    - install all dependencies

      Ubuntu/Debian
      ```sh
      apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev \
      libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev \
      libffi-dev
      ```
      RedHat/CentOS
      ```sh
      yum install gcc zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel \
      openssl-devel tk-devel libffi-devel curl
      ```
    - install pyenv
      ```sh
      curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash
      ```
    - in your ~.bashrc add this lines:
      ```sh
      export PATH="~/.pyenv/bin:$PATH"
      eval "$(pyenv init -)"
      eval "$(pyenv virtualenv-init -)"
      ```
    - restart your console and update pyenv:
      ```sh
      pyenv update
      ```

2) Setup default python
    - install your default python using pyenv e.g:
      ```sh
      pyenv install 3.6.6
      ```
      
    - set default python version e.g:
       ```sh
       echo "3.6.6" >> ~/.pyenv/version 
      ```

    - restart console and verify your default version python:
    ```sh
    python --version
    which python
    ```

3) Install pipenv
    ```sh
    pip install pipenv
    ```

4) Setup verification
    - create new empty directory for your project

    - add file named "Pipfile" with content:
       ```
       [[source]]
       url = "https://pypi.org/simple"
       name = "pypi"
       verify_ssl = true

       [dev-packages]

       [packages]
       Flask = "*"

       [requires]
       python_version = "3.6.4"
       ```
    - in this directory run command:
       ```sh
       >> pipenv install
     
       Warning: Python 3.6.4 was not found on your system...
       Would you like us to install CPython 3.6.4 with pyenv? [Y/n]: Y
       Installing CPython 3.6.4 with pyenv (this may take a few minutes)...
       ⠧Downloading Python-3.6.4.tar.xz...
       -> https://www.python.org/ftp/python/3.6.4/Python-3.6.4.tar.xz
       Installing Python-3.6.4...
       Installed Python-3.6.4 to /home/mbojanowski/.pyenv/versions/3.6.4


       Creating a virtualenv for this project...

5) Usefull links
- https://github.com/pypa/pipenv
- https://github.com/pyenv/pyenv
- https://github.com/pyenv/pyenv-installer

