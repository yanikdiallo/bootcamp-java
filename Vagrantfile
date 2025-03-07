
Vagrant.configure("2") do |config|
 

  config.vm.define "server" do |webserver|
    webserver.vm.box = "ubuntu/trusty64"


   webserver.vm.box_check_update = false
   webserver.vm.network "forwarded_port", guest: 8080, host: 8082
   webserver.vm.network "private_network", type: "static", ip: "192.168.0.10"
   webserver.vm.synced_folder "./tomcatwebapps", "/opt/tomcat/webapps"
   webserver.vm.provider "virtualbox" do |vb|
  
      vb.gui = false 

      vb.memory = "1024"
      vb.name = "Webserver-tomcat"
   end
  
  end

  config.vm.define "preprodserver" do |preprodwebserver|
    preprodwebserver.vm.box = "bento/ubuntu-22.04"


    preprodwebserver.vm.box_check_update = false
    preprodwebserver.vm.network "forwarded_port", guest: 8080, host: 8083
    preprodwebserver.vm.network "private_network", type: "static", ip: "192.168.0.11"
    preprodwebserver.vm.synced_folder "./tomcatwebapp", "/opt/tomcat/webapps"
    preprodwebserver.vm.provider "virtualbox" do |vb|
  
      vb.gui = false 

      vb.memory = "1024"
      vb.name = "preprodwebserver"
   end
  
  end



end
