# Busybox
Fork this repository before using it.

Create a Project in OpenShift called busybox

```
oc new-project busybox
```

Create a pipeline with parameters for the TAG_NUMBER, GIT_USER, GIT_PASSWORD, OCP_SERVER and OCP_TOKEN and choose pipeline defination from SCM in Jenkins. (This implmentation will work on a Jenkins master configured with the oc CLI)
