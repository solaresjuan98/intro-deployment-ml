- [What is DVC?](#what-is-dvc)
- [Setting up our environment](#setting-up-our-environment)
- [Implementing DVC](#implementing-dvc)


## What is DVC?

Data version control systems enable data scientists to track changes made to a dataset, compare different versions of the data, and revert to previous versions if needed. These systems also provide a history of changes made to the data

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
##  Install dvc
pip install dvc

## Installs git and the necessary plugins for google cloud storage
pip install dvc[gs]

##
dvc init

## 
export GOOGLE_APPLICATION_CREDENTIALS=$(realpath svcaccount.json)

```

2. In Google Cloud Storage create a new Bucket called `model-dataset-tracker`

3. Connect to Google Cloud storage

* `dvc remote` is used to add a new remote storage where a dataset can be stored.



```sh
dvc remote add dataset-track gs://<gcs_bucket_name>/dataset
```

```sh
dvc add dataset/opening_gross.csv --to-remote -r dataset-track
```

```sh
dvc add dataset/movies.csv --to-remote -r dataset-track
```

4. Model
```sh
## add remote
dvc remote add model-tracker gs://<gcs_bucket_name>/model

```

