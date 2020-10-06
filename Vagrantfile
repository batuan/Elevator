# -*- coding: utf-8 -*-
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

##### Vos Configurations
  config.vm.box = "m1reseaux"

  # Ajout d'une interface rÃ©seau (privÃ©e)
  config.vm.network "private_network", ip:"0.0.0.0", auto_config: false, virtualbox__intnet: "LAN" 


##### NE PAS MODIFIER CETTE PARTIE
  config.vm.hostname = File.basename(Dir.getwd)

  ### Dossiers partagÃ©s
  config.vm.synced_folder ".", "/vagrant", owner: "m1reseaux"
  config.vm.synced_folder "../partage", "/mnt/partage", create: true, owner: "m1reseaux" 

  # paramÃ¨tres virtualbox
  config.vm.provider "virtualbox" do |vb|
    vb.linked_clone = true  # performance
    # Commenter pour s'exÃ©cuter sans GUI
    vb.gui = true
    # MÃ©moire
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ['modifyvm', :id, '--graphicscontroller', 'vmsvga']
    vb.customize ["modifyvm", :id, "--vram", "16"]

    # Copier coller, pour virtualbox >= 6.1
    # vb.customize 'post-boot', ['controlvm', :id, 'clipboard', 'mode', 'bidirectional']
  end

end
