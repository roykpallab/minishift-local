# minishift-local

- start minishift

```
minishift profile set streams
minishift start --vm-driver virtualbox --memory "8GB" --cpus 2 

```



- Set up oc tool
```
minishift oc-env
#Then run this command 
SET PATH=C:\Users\roykp\.minishift\cache\oc\v3.11.0\windows;%PATH%
```

- Api based access 

```
oc login -u developer -p developer # login to openshift as developer 
oc whoami -t  # returns token 
# get projects information 
curl -k https://192.168.99.100:8443/oapi/v1/projects -H "Authorization: Bearer 6YigK8GDo05stvBVy9-hryojIlX07zO7S22J5GLjmiU"

```

- Login to minishift as system admin. Obtain projects and users 

```
oc login -u system:admin
oc get projects # get all the projects 
oc get users # get all users 

```

- Setup admin user in UI 
```
# first login via UI as administrator user using any password then run this command 

oc adm policy add-cluster-role-to-user cluster-admin administrator 


```

- get ip of the console 

```
minishift ip

```

- install kafka 

oc apply -f ./kafka/install/cluster-operator
oc create -f my-cluster.yml
oc create -f my-topic.yml
# see topics 
oc exec -it my-cluster-kafka-0 -c kafka -- bin/kafka-topics.sh --zookeeper localhost:2181 --describe


