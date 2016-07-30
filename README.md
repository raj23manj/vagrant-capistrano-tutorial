vagrant setup

follow here to setup 

https://github.com/mitchellh/vagrant

download vm and install from oracle 
download requireq VM box from boxes tab on vagrant site

issue for memory not sufficient

#https://github.com/mitchellh/vagrant/issues/2339#issuecomment-112402297

steps: 

vagrant box add ubuntu/trusty64 --box-version 20150609.0.9
cd ~/.vagrant.d/boxes/ubuntu-VAGRANTSLASH-trusty64/20150609.0.9/virtualbox/
VBoxManage clonehd box-disk1.vmdk tmp-disk.vdi --format vdi
VBoxManage modifyhd tmp-disk.vdi --resize 61440
VBoxManage clonehd tmp-disk.vdi resized-disk.vmdk --format vmdk
rm tmp-disk.vdi box-disk1.vmdk
mv resized-disk.vmdk box-disk1.vmdk


# df -h /
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        60G  1.8G   55G   4% /


issue for port not forwarding:

http://serverfault.com/questions/615809/vagrant-port-forwarding-does-not-work-without-any-error

http://stackoverflow.com/questions/5984217/vagrants-port-forwarding-not-working

http://stackoverflow.com/questions/23840098/empty-reply-from-server-cant-connect-to-vagrant-vm-w-port-forwarding



in the /etc/hosts change line 
127.0.0.1 localhost -> 0.0.0.0 localhost
and restart server


complete documentation:
https://www.vagrantup.com/docs/networking/private_network.html