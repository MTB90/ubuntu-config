## Anconda/conda configuration

### Install anaconda using pyenv

### Configration setup

* Run anaconda:
```console
pyenv shell anacondax3-x
```

* Setup conda for your shells:
```console
conda init zsh
conda init bash
```

* Disable anaconda to auto activate:
```
conda config --set auto_activate_base false
```

### Create venv and add to jupyter notebook

* Create venv using conda:
```console
conda create -n virtualenv-name
```

* Add venv kernel to jupyter notebook:
```console
conda activate virtualenv-name
conda install -c anaconda ipykernel

python -m ipykernel install --user --name=virtualenv-name
```

* Remove venv kernel to jupyter notebook:
```console
pyenv shell annaconda3-x
jupyter kernelspec uninstall virtualenv-name
```
