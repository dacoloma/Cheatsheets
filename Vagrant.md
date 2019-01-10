# Vagrant
## VirtualBox
Change the repository 
http://www.thisprogrammingthing.com/2013/changing-the-directory-vagrant-stores-the-vms-in/
## Vagrantfile
```ruby
Vagrant.configure("2") do |config|
  config.vm.box = "debian/stretch64"
  config.vm.synced_folder ".", "/git"
end
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY0MzE1NjQ1MiwxNTI5NjI2MjIzXX0=
-->