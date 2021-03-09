Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provider "hyperv"
  config.vm.network "public_network"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider "hyperv" do |h|
    h.enable_virtualization_extensions = true
    h.linked_clone = true
  end
end
