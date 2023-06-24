
Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-16.04"
# Contents of the data folder in the current dir is synced to the vm 
  config.vm.synced_folder "data/", "/vagrant_data"
  config.vm.provider "virtualbox" do |v|
    v.name = "cs61a-learning"
  end

   config.vm.provision "shell", inline: <<-SHELL
    wget http://inst.eecs.berkeley.edu/~scheme/precompiled/Linux/STk-4.0.1-ucb1.3.6.i386.rpm
    sudo apt-get install -y alien
    sudo apt-get install -y libsm6:i386
    sudo apt-get install -y libx11-6:i386
    sudo apt-get install -y libc6-i386 lib32stdc++6 lib32gcc1 lib32ncurses5 lib32z1
    fakeroot alien --target=amd64 STk-4.0.1-ucb1.3.6.i386.rpm
    sudo dpkg -i --force-architecture stk_4.0.1-1_amd64.deb
   SHELL
end
