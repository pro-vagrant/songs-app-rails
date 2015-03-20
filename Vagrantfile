Vagrant.configure(2) do |config|
  config.vm.box = "rails-v0.5.5"
  config.vm.box_url = "http://boxes.gajdaw.pl/rails/rails-v0.5.5.box"
  config.vm.box_download_checksum_type = "sha256"
  config.vm.box_download_checksum = "0d20b0f90d0ffc483039edb69448d80b0f0440bcc926a5341e2f70af08b76960"
  config.vm.network :forwarded_port, guest: 3000, host: 3000, host_ip: "127.0.0.1"

$script = <<SCRIPT

cd /vagrant
rails server -b 0.0.0.0 -d

SCRIPT

  config.vm.provision "shell", inline: $script, run: "always"

  config.vm.post_up_message = "The application is available at http://127.0.0.1:3000"
end
