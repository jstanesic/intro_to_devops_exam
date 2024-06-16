# intro_to_devops_exam

## Configuring your VM to access internal OpenShit

## Accesing the console
URL to console is: https://console-openshift-console.apps.vuacloud.vua.cloud/
Accept and ignore certificate errors.

Select studenti2023-2024.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/99ad752c-2145-48cd-8ff4-3483847d2cc4)

Use your infoeduka username and password you received trough email.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/1ab2891a-996f-4e6b-8c7d-01189f752e87)

Make sure that under clusters, local-cluster is selected.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/5ff3bbc0-35b0-44e1-b419-a156a7a8af84)

Use the project with the same name as you infoeduka username.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/2aa2a067-1344-4fe8-b021-29754a78f85f)


oc tool is available to download trough the cluster, by navigating to help menu, Command Line Tools and then selecting correct binary.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/abae3036-ef6d-46c4-97bc-0ab13550c02f)


To login trough CLI, use the following command:
```
oc login -u <username> --server=https://api.vuacloud.vua.cloud:6443/
```
You will be prompted for a password.

## Learning Outcome 5 task 3 Note
It is okay if the pod does not start due to some erros but the deployment should create successfully.

## Disk space issues

If during the exam you run into an issue that you are missing disk space on the VM you can do the following:

```
# Remove ALL containers and ALL images
podman rmi -a -f
# Remove cache of packages
rm -rf /var/cache/PackageKit
# Remove Google Chrome
su -
dnf remove google-chrome
```
