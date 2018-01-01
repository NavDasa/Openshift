# Openshift
A complete Linux Redhat 7 Openshift


First In order to get ahead of Openshift, First of all we has to set up a KVM for master, and also some Nodes. And it has to be done in the Linux environment Redhat7. ISO Image.

Login as a Root User and also Install the fallowing command for, Also create an Account in Redhat.


                    subscription-manager register (Enter username and passwd)

In order to attach Entitilments to attachneeded:

    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A18 "Red Hat Enterprise Linux Server Entry Level, Self-support" \ | grep "Pool ID" | awk '{print$3}')


In order to Redhat openshift attach:

    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A32 "Red Hat OpenShift Container Platform" \ | grep "Pool ID" | awk '{print$3}')


Note: We can play with 10 licences

we have to assign the Redhat Enterprise openstack autonomus for the server, that was specificly openB switch, for those who are launching on redhat Enterprise as linux or community versions
If you don't have access to the RHOHP licencse, we can just enable Apple Repository, Extra packages for Enterprise linux from there we can find openb switch. 

If you have openshift licence available, you can go ahead and use it below command

    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A29 "Red Hat OpenStack Platform" \ |grep -B3 "Unlimited" \ | grep "Pool ID" | awk '{print$3}')


First thing we have to do disable the current repos:

    subscription-manager repos --disable=*

Enable our Repository's

    subscription-manager repos --enable=rhel-7-server-rpms \ --enable=rhel-7-server-optional-rpms \ --enable=rhel-7-server-extras-rpms \ --enable=rhel-7-server-ose-3.5-rpms \ --enable=rhel-7-server-openstack-10-rpms

    yum repolist (confirm with yum repo list)

    yum -y update

    systemctl reboot

    logout & login again
    
Note : Now our Master Node is Configured.

KVM Setup for Node1:

Setup a 4 Gb, 4096 MB RAM, CPU 2, storage from EXTK3DK available, Give server name : Node1, Virtual network:


Configuring the openshift node: 40 GB for Virtual Block storage, Any Network DNS name, give the Manual IP, Launch the Installation 

Add a Block storage Volume for docker storage, 40 GB for Docker Storage. 

Login to the terminal window:

      fdisk -l

Check that block storage volume is attached to the volume.

Setup 

    Subscription-manager register ( Give credentials and login)


In order to attach Entitilments to attachneeded:

    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A18 "Red Hat Enterprise Linux Server Entry Level, Self-support" \ | grep "Pool ID" | awk '{print$3}')


In order to Redhat openshift attach:

    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A32 "Red Hat OpenShift Container Platform" \ | grep "Pool ID" | awk '{print$3}')

If you have openshift licence available, you can go ahead and use it below command


    subscription-manager attach --pool=$(subscription-manager list --available \ | grep -A29 "Red Hat OpenStack Platform" \ |grep -B3 "Unlimited" \ | grep "Pool ID" | awk '{print$3}')


First thing we have to do disable the current repos:

    subscription-manager repos --disable=*

Enable our Repository's

    subscription-manager repos --enable=rhel-7-server-rpms \ --enable=rhel-7-server-optional-rpms \ --enable=rhel-7-server-extras-rpms \ --enable=rhel-7-server-ose-3.5-rpms \ --enable=rhel-7-server-openstack-10-rpms

    yum repolist (confirm with yum repo list)

    yum -y update

    systemctl reboot

    logout & login


 Note : The configuration is same as the Master.
 
 
              
     
