# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false
  config.vm.network :private_network, ip: "192.168.2.16"
  config.vm.hostname = "utils.vagrant.eatsleeplim.com"

  module OS
    def OS.windows?
        (/cygwin|mswin|mingw|bccwin|wince|emx/ =~ RUBY_PLATFORM) != nil
    end

    def OS.mac?
        (/darwin/ =~ RUBY_PLATFORM) != nil
    end

    def OS.unix?
        !OS.windows?
    end

    def OS.linux?
        OS.unix? and not OS.mac?
    end
  end

  if OS.mac?
    config.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = 2048
    end
  end
end
