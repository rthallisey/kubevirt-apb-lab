# KubeVirt APB Lab

#### Deploy OpenShift/Kubernetes
There are many ways to deploy OpenShift and Kubernetes.  If you already have an
existing cluster or know want to use a different guide for setting up a cluster
then you can skip this section.  This guide will use ```oc cluster up``` to
deploy:
 - Single node OpenShift cluster
 - Service-Catalog
 - Ansible-Service-Broker

```bash
docker cp $(docker create docker.io/openshift/origin:v3.10):/usr/bin/oc ~/bin/oc

TAG=v3.10 oc cluster up --tag=${TAG} --image=docker.io/openshift/origin-\\${component}:\\${version} --enable=service-catalog,template-service-broker,router,registry,web-console,persistent-volumes,sample-templates,rhel-imagestreams,automation-service-broker

oc login -u admin -p admin
```

#### Run the KubeVirt APB
Open the console UI in your browser located at: ```https://<my_ip>:8443/console```

![Service Catlog UI](service-catalog-ui.png)

![KubeVirt APB Info](kubevirt-apb-info.png)

![Configure the KubeVirt APB](configured-kubevirt-apb.png)

![Create the KubeVirt APB](create-kubevirt-apb.png)
