# 100 - Install the Doppler CLI in GitPod

See [GitPod](https://docs.doppler.com/docs/gitpod).

To test if the Doppler secrets (i.e. the environment variables hosted in Doppler) are accessible and set, run:

```
$ doppler secrets
```

You will be prompted alike following:

| NAME | VALUE | NOTE |
| ----- | ---- | ---- |
| API_TOKEN | github_pat_********** | |
| DOPPLER_CONFIG | dev | |
| DOPPLER_ENVIRONMENT | dev | |
| DOPPLER_PROJECT | agility-game-kener | |
| GH_TOKEN | github_pat_******** | |

To run the application's start (e.g., build) command, prefix it as follows (NOTE: including the ```--```):

```
$ npm install -g npm@10.4.0 && npm install && doppler run --mount .env -- npm run build
```

**NOTE**: If set up in .gitpod.yml, this would become:

```
image:
  file: .gitpod.Dockerfile

tasks:
  - before: | 
      doppler configure set token $DOPPLER_LOCAL_TOKEN
      doppler setup --project agility-game-kener --config dev
      mkdir -p ./static/kener
  - init: |
      npm install -g npm@10.4.0
      npm install
      export PUBLIC_KENER_FOLDER=/workspace/kener/static/kener
      export NODE_ENV=production
      export PORT=3000
      export API_IP=127.0.0.1
      export MONITOR_YAML_PATH=./config/monitors.yaml
      export SITE_YAML_PATH=./config/site.yaml
      doppler run -- npm run kener:build
```

The Doppler environment variables (here: GH_TOKEN and API_TOKEN) will thus be injected in the environment, whilst at the same time injecting any environment variables that are exported from the ```.gitpod.yml``` file (mostly, non-secret variables), such as PUBLIC_KENER_FOLDER 

And then **manually**:
1. copy the file ```config/monitors.example.yaml``` to ```config/monitors.yaml``` and apply any changes - if required - in the copy.
2. copy the file ```config/site.example.yaml``` to ```config/site.yaml``` and apply any changes - if required - in the copy.
3. run the following command from the terminal:

```
$ npm run kener
```
