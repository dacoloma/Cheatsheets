# Vagrant
## VirtualBox
First, create a repo (named vagrant here) where VMs will be store 
```bash
$ mkdir /path/to/VMs/vagrant
$ echo 'export VAGRANT_HOME=/path/to/VMs/vagrant' >> ~/.zshrc
```
In VirtualBox settings, change the default VMs storing repo.
> http://www.thisprogrammingthing.com/2013/changing-the-directory-vagrant-stores-the-vms-in/
## Vagrantfile
Create a file named Vagrantfile a put it in vagrant repo.
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.synced_folder ".", "/git"
end
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM4OTc5ODM1NywxNTI5NjI2MjIzXX0=
-->