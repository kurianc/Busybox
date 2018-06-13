node('master') {
    stage('Git clone OpenShift Template...') {
        sh 'rm -rf Busybox'
        sh 'git clone ${GIT_URL}'
    }
    stage('Login to openshift cluster...') {
        sh 'oc login ${OCP_SERVER} --token=${OCP_TOKEN}'
    }
    stage('Busybox project...') {
        sh  'oc project busybox'
    }
    stage('Delete all busybox resources...') {
        sh  'oc delete all -l app=busybox-http-app'
        sh returnStatus: true, script: 'oc delete configmap busybox-http-app'
    }
    stage('Tag application...') {
        sh  'oc tag docker.io/openshift/busybox-http-app:latest busybox-http-app:${TAG_NUMBER}'
    }
    stage('Deploy busybox...') {
	sh 'oc create configmap busybox-http-app --from-file=Busybox/application.properties'
        sh 'oc process -f Busybox/busybox-http-app.yaml -p TAG_NUMBER=${TAG_NUMBER} | oc apply -f -'
    }
    stage('Cleanup git clone...') {
        sh 'rm -rf Busybox'
    }
}
