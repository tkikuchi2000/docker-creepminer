docker-creepminer
=================
Out-of-the-box creepMiner github build running in Ubuntu 16.04.4

![ceepMiner](https://i.imgur.com/KsPZaKu.png)

## Usage

Start your image binding the external ports 8124 and 9001 to all interfaces to your container:
```
docker create \
--name=creepMiner \
-e AUTO_START=TRUE \
-e TZ=<timezone> \
-p 8124:8124 \
-p 9001:9001 \
-p 9002:9002 \
-v </path/to/config>:/config
-v </path/to/plot_dir_01>:/plot/01 \
-v </path/to/plot_dir_02>:/plot/02 \
linuxserver/plex
```

By default the miner uses a default config `/usr/local/sbin/miner.config`. 

Please use your own [`miner.confg`](https://github.com/Creepsky/creepMiner/wiki/Sample-mining.conf).

Place your [`miner.confg`](https://github.com/Creepsky/creepMiner/wiki/Sample-mining.conf) in `</path/to/config>`.

## Quick setup

Go to [http://127.0.0.1:8124](http://127.0.0.1:8124) and setup your miner.

Please see the creepMiner [wiki](https://github.com/Creepsky/creepMiner/wiki) for futher information on setting up your miner.

## Connecting to the container

Interface | URL and Port
------------ | -------------
creepMiner | [http://docker_ip:8124](http://127.0.0.1:8124)
supervisord /webproc | [http://docker_ip:9001](http://127.0.0.1:9001)
frontail | [http://docker_ip:9002](http://127.0.0.1:9002)

## Advanced settings

### creepMiner auto start
To enable or disable creepMiner from auto starting use the 
AUTO_START environment variable to TRUE/FALSE

### ssh login to container
If you wish to enable ssh for the container set
ENABLE_SSH to TRUE

### supervisord or webproc deamons
dependent on your needs TBD
SUPERVISOR environment variable to TRUE/FALSE
WEBPROC

## Other information

Description | URL
------------ | -------------
creepMiner github | [https://github.com/Creepsky/creepMiner](https://github.com/Creepsky/creepMiner)
creepMiner pool | [https://pool.creepminer.net](https://pool.creepminer.net)
creepMiner wallet | [https://wallet.creepminer.net](https://wallet.creepminer.net)
demo miner | [https://demo.creepminer.net](https://demo.creepminer.net)

Please see docker's [Use volumes](https://docs.docker.com/storage/volumes/) for more details.