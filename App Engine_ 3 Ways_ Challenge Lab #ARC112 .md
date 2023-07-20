# ARC112
### Run in cloudshell [add your message inside "" eg: "Hello World!" ]
```cmd
export MESSAGE=""
```
```cmd
gcloud services enable appengine.googleapis.com
git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
cd python-docs-samples/appengine/standard_python3/hello_world
gcloud app deploy
rm -f main.py
cat > main.py << EOF

from flask import Flask

app = Flask(__name__)

@app.route("/")
def hello():
    return "$MESSAGE"

if __name__ == "__main__":
    app.run(host="127.0.0.1", port=8080, debug=True)

EOF
gcloud app deploy
echo -e "\033[32mNow type Y then enter again enter then type N when asked\033[0m"
gcloud compute ssh "lab-setup"
```
```cmd
git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
cd python-docs-samples/appengine/standard_python3/hello_world
exit
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
