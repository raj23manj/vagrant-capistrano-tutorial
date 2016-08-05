vagrant setup

this is the "local machine as server" in case to redo git hash

45be145aa118bae5c5af91c27883fec050511c6e

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


without binding for port forwarding

rails s -b 0.0.0.0
# run from guest, from VM instance



complete documentation:
https://www.vagrantup.com/docs/networking/private_network.html



Deploying to VPS:
6:49 time for new user "deployer" in 335

steps:

sudo adduser deployer --ingroup admin
#add password, fill detials if needed
#change to that user
su deployer

capistrano 
revised & pro aswell
rails casts
335, 133, 337



deploying to vagrant-capistrano

https://dzone.com/articles/capistrano-deploying-vagrant



find ip for vagrant

http://stackoverflow.com/questions/14870900/how-to-find-vagrant-ip

http://stackoverflow.com/questions/10353530/is-there-a-way-to-deploy-into-a-vagrant-vm-using-capistrano


use rbenv-installer

see 335 for details

time 7:30

to reload 
source ~/bash_profile








https://github.com/mitchellh/vagrant/wiki/Available-Vagrant-Plugins



