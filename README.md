# milestone-demos

This repository contains the yaml files used for the release workstream HACBS milestone demos.

These yaml files assume you have bootstrapped a working appstudio configuration from [infra-deployments](https://github.com/redhat-appstudio/infra-deployments).

## Searching for previous demos

Milestones are separated in this repository by tags.
To view the demo resources for a previous milestone, simply checkout its tag.
Be warned, however, that we make no guarantee that the past demo resources work with the latest HACBS deployment.
Once a milestone passes, we will only be focusing on demo resources for the next milestone.
So, if you need working demo resources, use the `main` branch.

## Running the current demo
### Bootstrapping

After bootstrapping the cluster with App Studio, you can prepare the demo by running the [bootstrap.sh](./bootstrap.sh) script.
```
$ git clone https://github.com/hacbs-release/milestone-demos.git
$ ./bootstrap.sh
```
This will create all the required resources to run the demo. Those are:
* Demo resources in the base directory.
* Quay secret to pull and push images (a password to the robot account will be requested).
* Cosign secret with the public key extracted from tekton-chains.

### Triggering the demo

To trigger the demo, the only thing needed after bootstrapping is to apply the [release.yaml](./release.yaml) file, which will create a new Release in the cluster.
