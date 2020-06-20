# vagrant-provision-centos-7-with-docker-install

simple vagrant file to create centos 7 machine.

NOTES to consider:

1- I used public network, so.. <br />
please check your network IP config and change it <br />

2- for the shared folder\
shutdown all running VMs\
update vagrant to latest version\
update virtual box to latest version\
download and install Oracle VM VirtualBox Extension Pack and install it <br />

you need to restart Windows for those update!\
typical windows right ¯\\_(ツ)_/¯ <br />

run the following commands:\
vagrant plugin install vagrant-vbguest\
vagrant vbguest <br />

it may ask you to run the VM:\
vagrant up <br />

you should be all set!
