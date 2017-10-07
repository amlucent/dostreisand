# See documentation/testing.md for instructions on using this Vagrantfile
#
Vagrant.require_version ">= 1.9.0"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/xenial64"
  # Old box: bento/ubuntu-16.04

  config.vm.define "streisand-host", primary: true do |streisand|
    streisand.vm.hostname = "streisand-host"
    streisand.vm.network :private_network, ip: "10.0.0.10"
    streisand.vm.network "forwarded_port", guest: 22, host: 2022, id: "ssh", auto_correct: true
    streisand.vm.provision "ansible" do |ansible|
      # NOTE: Uncomment the below line for verbose Ansible output
      # ansible.verbose = "v"
      ansible.playbook = "playbooks/vagrant.yml"
      ansible.host_vars = {
        "streisand-host" => {
          # Don't prompt or pause during the playbook runs
          "streisand_noninteractive" => true,
          # Do copy the files required by the client test locally
          "streisand_client_test" => true,
          "streisand_ipv4_address" => "10.0.0.10"
        }
      }
      ansible.raw_arguments  = [
        "--extra-vars=@global_vars/vars.yml",
        "--extra-vars=@global_vars/default-site.yml"
      ]
    end
  end

  config.vm.define "streisand-client" do |client|
    client.vm.hostname = "streisand-client"
    client.vm.network :private_network, ip: "10.0.0.11"
    client.vm.network "forwarded_port", guest: 22, host: 2122, id: "ssh", auto_correct: true
    client.vm.provision "ansible" do |ansible|
      # NOTE: Uncomment the below line for verbose Ansible output
      #ansible.verbose = "v"
      ansible.playbook = "playbooks/test-client.yml"
      ansible.host_vars = {
        "streisand-client" => {
          "streisand_ip" => "10.0.0.10",
        }
      }
    end
  end
end
