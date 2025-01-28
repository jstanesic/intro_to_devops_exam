# intro_to_devops_exam

## Configuring your VM to access internal OpenShit
As user root execute the following command to add another line to your /etc/hosts file
```
echo "10.10.68.126 console-openshift-console.apps-crc.testing api.crc.testing api.crc.testing canary-openshift-ingress-canary.apps-crc.testing console-openshift-console.apps-crc.testing default-route-openshift-image-registry.apps-crc.testing downloads-openshift-console.apps-crc.testing oauth-openshift.apps-crc.testing registry.apps.vuacloud.vua.cloud" >> /etc/hosts
```
Your /etc/hosts should look like this
![image](![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/bb582af1-bb79-407c-a2b8-191e6bee0497))

To switch to user root execute the following command, password is centos:
```
su -
```

## Accesing the console
URL to console is: https://console-openshift-console.apps-crc.testing
Accept and ignore certificate errors.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/fd46d3a2-d48b-441e-937b-947c3be41168)

You should have received username and password on your emails.

## Installing oc tool
To download the oc tool log in to the OpenShift cluster. Click on the ? question mark in the top right corner. Select Command line tools.
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/cbffcf42-e0d1-438c-95be-5f88fa4df0bf)


Select Download oc tool for Linux for x86_64

![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/6bec537e-f2df-46ed-8013-4dca35b48270)

File called oc.tar will be downloaded under /home/student/ directory.

Execute the following commands to be able to use the oc tool:
```
tar -xf oc.tar
rm oc.tar
chmod ugo+x oc
su -
mv /home/student/oc /usr/bin/oc
oc
```
![image](https://github.com/jstanesic/intro_to_devops_exam/assets/91891125/1e57c1a7-507f-44eb-88b3-428ae9873de5)


To login trough CLI, use the following command:
```
oc login -u <username>
```
You will be prompted for a password.

## Disk space issues

If during the exam you run into an issue that you are missing disk space you can do the following:

```
# Remove ALL containers and ALL images
podman rmi -a -f
# Remove cache of packages
rm -rf /var/cache/PackageKit
# Remove Google Chrome
su -
dnf remove google-chrome
```
