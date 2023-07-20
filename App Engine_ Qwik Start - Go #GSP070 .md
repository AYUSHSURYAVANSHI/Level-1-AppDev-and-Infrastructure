# GSP070
```cmd
export REGION=
```
```cmd
gcloud config set compute/region $REGION
gcloud services enable appengine.googleapis.com
git clone https://github.com/GoogleCloudPlatform/golang-samples.git
cd golang-samples/appengine/go11x/helloworld
sudo apt-get install google-cloud-sdk-app-engine-go
gcloud app deploy
gcloud app browse
```
____
# REGIONS
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
