
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

   config.vm.box = "centos/7"
   config.ssh.insert_key = false
   config.ssh.shell = 'bash --noprofile -l'

   config.vm.define "app" do |app|

       app.vm.network "private_network", ip: "192.168.0.151"
       app.vm.hostname = "mpass-proxy.local"
       app.vm.provision :ansible do |ansible|
           ansible.galaxy_role_file = 'requirements.yml'
           ansible.playbook = "mpass-proxy.yml"

       end

   end

   config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777", "fmode=666"]


end

