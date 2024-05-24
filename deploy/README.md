# Deploying toolbox-container on OpenShift using Kustomize

Modify [kustomization.yaml](kustomization.yaml) to your liking. You can uncomment many of the optional settings there to activate them.

Deploy the toolbox-container container using:

```
oc oc apply --kustomize .

or

argocd app create toolbox \
--repo https://github.com/mmwillingham/toolbox-container.git \
--path deploy --dest-server https://kubernetes.default.svc \
--sync-policy automated \
--self-heal \
--sync-option Prune=true \
--dest-namespace toolbox

```
