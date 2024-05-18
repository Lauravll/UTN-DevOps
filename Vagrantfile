Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  # Redirigir el tráfico web de la VM al puerto 8080 de la máquina Host (su propia computadora).
  config.vm.network "forwarded_port", guest: 80, host: 8080

  # Mapear la carpeta del proyecto de la máquina Host al directorio "/vagrant" en Ubuntu.
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2
  SHELL
end
