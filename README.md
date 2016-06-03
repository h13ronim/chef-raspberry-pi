# Raspberry Pi with Chef Solo (Example configuration)

* Install Raspbian Jessie Lite on Raspberry Pi. For example via [BerryBoot](http://www.berryterminal.com/doku.php/berryboot).
* Copy your SSH public key to Raspberry Pi.
* Install [ChefDK](https://downloads.chef.io/chef-dk/) on your machine.
* Install [knife solo](https://matschaffer.github.io/knife-solo/):

```bash
chef gem install knife-solo
```

### Run

```bash
knife solo bootstrap pi@192.168.1.201
```

### Known issues:

#### `chef-solo: command not found`

https://github.com/matschaffer/knife-solo/issues/373, solution: https://github.com/matschaffer/knife-solo/pull/454/files

#### `rack requires Ruby version >= 2.2.2.`

Rubygems update resolves it:

```
pi@raspberrypi:~ $ sudo gem install rubygems-update
pi@raspberrypi:~ $ sudo update_rubygems
```
