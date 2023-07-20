# GSP023
### Run in cloudshell
### Select us-central when asked to select
### And to select us-central type 10
```cmd
gcloud storage cp -r gs://spls/gsp023/flex_and_vision/ .
cd flex_and_vision
export PROJECT_ID=$(gcloud config get-value project)
gcloud iam service-accounts create qwiklab \
  --display-name "My Qwiklab Service Account"
gcloud projects add-iam-policy-binding ${PROJECT_ID} \
--member serviceAccount:qwiklab@${PROJECT_ID}.iam.gserviceaccount.com \
--role roles/owner
gcloud iam service-accounts keys create ~/key.json \
--iam-account qwiklab@${PROJECT_ID}.iam.gserviceaccount.com
export GOOGLE_APPLICATION_CREDENTIALS="/home/${USER}/key.json"
virtualenv -p python3 env
source env/bin/activate
pip install -r requirements.txt
gcloud app create
export CLOUD_STORAGE_BUCKET=${PROJECT_ID}
gsutil mb gs://${PROJECT_ID}
python main.py
```
____
[Click me and download the image you will need this in further steps](https://api.time.com/wp-content/uploads/2020/09/time-100-Sundar-Pichai.jpg)
### Open web preview in port 8080 and upload the image and click submit
### Then come back to the cloudshell and press Ctrl + C to stop the script
____
### Run in cloudshell
```cmd
rm -f app.yaml
cat > app.yaml << EOF
runtime: python
env: flex
entrypoint: gunicorn -b :\$PORT main:app

runtime_config:
  python_version: 3.7

env_variables:
  CLOUD_STORAGE_BUCKET: $PROJECT_ID

manual_scaling:
  instances: 1

EOF
gcloud config set app/cloud_build_timeout 1000
gcloud app deploy
```
____
# REGIONS (USE us-central only for this lab)
`1` *=>* `asia-east1`<br>
`2` *=>* `asia-northeast1`<br>
`3` *=>* `asia-south1`<br>
`4` *=>* `asia-southeast1`<br>
`5` *=>* `australia-southeast1`<br>
`6` *=>* `europe-central2`<br>
`7` *=>* `europe-west`<br>
`8` *=>* `europe-west2`<br>
`9` *=>* `europe-west3`<br>
`10` *=>* `us-central`<br>
`11` *=>* `us-east1`<br>
`12` *=>* `us-east4`<br>
`13` *=>* `us-west1`<br>
`14` *=>* `us-west2`<br>
`15` *=>* `us-west3`<br>
`16` *=>* `us-west4`<br>
`17` *=>* `cancel`
