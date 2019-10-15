# argo-nginx-test


## Argo Setup

Setup argo on a cluster using the "Getting Started" from the argo website:

    https://argoproj.github.io/argo-cd/getting_started/

## Setup this example

Once argo is running on the cluster, setup this public repo.

Then tested this setup using:

    argocd app create nginx-test \
    --repo https://github.com/CariZa/argo-nginx-test.git \
    --path ./ \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default

Path is ./ because the yaml files are in the root folder level.

Left destination server (--dest-server) as: https://kubernetes.default.svc

Because argo is running on the server I am running this test on.

Left namespace (--dest-namespace) as default, change if you want to test on another namespace.


## Notes

Check on the argo app:

    argocd app get nginx-test

Sync:

    argocd app sync nginx-test

Delete:

    argocd app delete nginx-test