# DIY Deploy Secrets

Demo repo to deploy secrets to K8s cluster using SLV

## Try it

- Install SLV from [here](https://github.com/amagioss/slv?tab=readme-ov-file#installation)
- Setup profile by following instructions from [here](https://github.com/slvdemo/profile?tab=readme-ov-file#how-to-setup)
- Fork [this repo](https://github.com/slvdemo/secrets/fork)
- Optionally, create a new K8s compatible SLV vault inside the `secrets` directory using the following command
```sh
slv vault new -v secrets/example.slv.yaml --k8s example -s demo-k8s
```
- Add secrets to any vaults inside the `secrets` directory. Make sure the k8s name is unique (preferrably one that matches the name of the file prefixing `.slv.yaml`)
```sh
slv vault put -v secrets/example.slv.yaml -n hello --secret "Welcome to SLV"
```
- Send a pull request
- Wait for the pull to be merged and once the pipeline runs, observe changes at `https://bh.security.amagi.tv/secret/blackhat`. Replace `blackhat` with the k8s secret name (the one that you had passed to the `--k8s`flag).