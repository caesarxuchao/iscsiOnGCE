This is an alternative setup for [GoogleCloudPlatform/kubernetes/examples/iscsi](https://github.com/GoogleCloudPlatform/kubernetes/tree/master/examples/iscsi).

Setup on Ubuntu 12.04 and Debian 7 on GCE

GCE does not provide preconfigured Fedora 21 image, so I set up the iSCSI target on a preconfigured Ubuntu 12.04 image, mostly following these instructions(http://www.server-world.info/en/note?os=Ubuntu_12.04&p=iscsi). I made necessary changes such as creating two logical volumes and two LUN, because the iscsi.json in this example expects such a setup.

I had kernel mismatch problems when setting up iSCSI target on other preconfigured GCE images. Using the Ubuntu 12.04 image makes the life much easier.

My Kubernetes cluster was running on Debian 7 nodes, so I followed these instructions(http://www.server-world.info/en/note?os=Debian_7.0&p=iscsi&f=2) to set up the iSCSI initiator. Remember to format the iSCSI devices to match the settings in the iscsi.json.
