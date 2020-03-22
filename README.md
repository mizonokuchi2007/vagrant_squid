# vagrant_squid
Vagrantfile to set up squid as a forward proxy server.

## usage
1. git clone
2. vagrant up

squid is running at 10.0.0.80:8080.

## from vagrant
1. install the vagrant proxy plugin:
```
vagrant plugin install vagrant-proxyconf
```

2. add proxy settings to Vagrantfile or global Vaglant configulation(~/.vagrant.d/Vagrantfile)
```
Vagrant.configure("2") do |config|
  # Enable caching web server
  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "http://10.0.0.80:8080/"
    config.proxy.https    = "http://10.0.0.80:8080/"
    config.proxy.no_proxy = "localhost,127.0.0.1"
  end
end
```
