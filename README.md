# Busybox
Fork this repository before using it.

Create a Project in OpenShift called busybox

```
oc new-project busybox
```

Create a pipeline with string parameters for the TAG_NUMBER, GIT_URL, OCP_SERVER and OCP_TOKEN and choose pipeline defination from SCM in Jenkins and point it to your GIT repo. (This implmentation will work on a Jenkins master configured with the oc CLI)

