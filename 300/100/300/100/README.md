# 100 - Install the Doppler CLI in GitPod

See [GitPod](https://docs.doppler.com/docs/gitpod).

In short:

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
...
tasks:
  ...
  -  init: |
       npm install -g npm@10.4.0
       npm install
```

And then **manually** run the following command from the terminal, AFTER having configured the ```.env``` file (as well as the ```config/monitor.yaml``` and ```config/site.yaml``` files):

```
$ doppler run --mount .env -- npm run build
```

The Doppler environment variable will thus be injected in the environment, whilst at the same time injecting any environment variables that are stored in a .env file (mostly, non-secret variables). 
