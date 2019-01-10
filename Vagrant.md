# Vagrant
## VirtualBox
```bash
$ mkdir /path/to/VMs/vagrant
$ echo 'export VAGRANT_HOME=/Volumes/Storage/goinfre/<login>/vagrant' >> ~/.zshrc
```
Change the repository where vagrant will be used
http://www.thisprogrammingthing.com/2013/changing-the-directory-vagrant-stores-the-vms-in/
## Vagrantfile
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.synced_folder ".", "/git"
end
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgxNDE4MjQ3MSwxNTI5NjI2MjIzXX0=
-->