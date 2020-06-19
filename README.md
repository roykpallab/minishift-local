# Minishift Installment Instructions
- Install oracle virtualbox 
- Download updated minishift disbribution for linux and extract it in your preferred location 
- Add minishift to your path ``` export PATH=<extracted minishift path>:$PATH ```
- Run this command to start minishift ```minishift start --vm-driver=virtualbox```
- Add oc tool to your system path using this command ``` eval $(minishift oc-env) ```

- Login as admin user ```oc login -u system:admin```
- Login to minishift UI using developer username and password
- Make the developer user cluster admin using this command ```oc adm policy add-cluster-role-to-user cluster-admin developer ```

- Install helm on minishift 
https://github.com/ocd-scm/ocd-meta/wiki/Helm-Tiller-on-Minishift