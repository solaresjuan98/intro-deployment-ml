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
##
dvc init

## 
export GOOGLE_APPLICATION_CREDENTIALS=$(realpath svcaccount.json)

```

2. In Google Cloud Storage create a new Bucket called `model-dataset-tracker`

3. Connect to Google Cloud storage

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

