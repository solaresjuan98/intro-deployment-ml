- [Setting up our environment](#setting-up-our-environment)
- [Implementing DVC](#implementing-dvc)


## Setting up our environment

1. Install pip3
2. Install virtualenv
3. Create new virtualenv and enable it
```sh
virtualenv venv
source venv/bin/activate
```
4. Install notebook requierements
```sh
pip install -r notebooks/requirements.txt
```
5. Install jupyter notebook
```sh
pip install jupyter
```
6. Enable jupyter notebook
```
jupyter notebook
```

## Implementing DVC 

1. In the venv environment, install dvc
```sh
pip install dvc
##
pip install dvc[gs]
```