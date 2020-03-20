# server-for-laravel
One-time fully automated shell script to install all needed software to run Laravel on Ubuntu 18.04 LTS. Creates user, installs ufw, nginx, php, nodejs/yarn, MariaDB/MySQL, PostgreSQL, Let's Encrypt/Certbot. Optional parameters available.

[![asciicast](https://asciinema.org/a/311864.svg)](https://asciinema.org/a/311864)

>To understand what is installed, check Options section

### Recommended requisites
- **Ubuntu 18.04 LTS** ~~or at least newer~~ (not recommended)
- **root**/sudo as current user
- `curl` or `wget` should be installed
- a new server. We are not responsible for any loss you may suffer. 
### Basic Installation

This script is installed by running one of the following commands in your terminal. You can install this via the command-line with either `curl` or `wget`.

>**_At the end you'll receive a report with all passwords. Keep it safe._**
#### via curl

```shell
bash -c "$(curl -fsSL https://raw.githubusercontent.com/insign/server-for-laravel/master/install.sh)"
```

#### via wget

```shell
bash -c "$(wget -qO- https://raw.githubusercontent.com/insign/server-for-laravel/master/install.sh)"
```
#### Manual inspection

It's a good idea to inspect the install script from projects you don't yet know. You can do
that by downloading the install script first, looking through it so everything looks normal,
then running it:

```shell
curl -Lo install.sh https://raw.githubusercontent.com/insign/server-for-laravel/master/install.sh
bash install.sh
```

## Parameters (all optional)
* `-u|--user` - set new user name. Default: laravel
* `-p|--pass` - set new user password. Default is _random_ (shown at the end)
* `--dont-create-new-user` - don't creates a new user (not recommended)
* `--keep-existing-user` - keep existent user if it exists
* `--skip-swap` - skip creation swapfile (not recommended unless already exists)
* `--swap-size` - set swap file size in MB. Default is 2048 (2GB)
* `--skip-updates` - Skip updates and upgrade the system (not recommended)
* `--no-omz` - don't install oh-my-zsh framework (not recommended)
* `--no-ufw` - don't install or configure UFW firewall (not recommended)
* `--no-nginx` - don't install or configure nginx
* `--no-php` - don't install or configure php
* `--no-node` - don't install or configure yarn/node/npm
* `--no-mysql` - don't install or configure mysql (MariaDB actually)
* `--my-pass-root` - set the mysql root password. Default is _random_ (shown at the end)
* `--my-pass-user` - set the mysql user password. Default is _random_ (shown at the end)

>Soon
* `--no-postgres` ~~- don't install or configure postgresql~~
* `--no-lets-encrypt` - ~~don't install or configure let's encrypt / certbot~~

## Examples
### Web Server (with nginx & php)
```shell
bash -c "$(curl -fsSL https://raw.githubusercontent.com/insign/server-for-laravel/master/install.sh)" "" --no-mysql --no-postgres
```
### Database Server
>Soon
### Cache Server
>Soon


## Roadmap
- [ ] Finish postgresql installation
- [ ] Finish Let's Encrypt installation
- [ ] Finish supervisord installation
- [ ] Enable better gzip config for nginx by default
- [ ] Generate ssh key
- [ ] Import private key
- [ ] Remove password login (ssh key only)
- [ ] Support for multiple php versions https://github.com/wilmoore/php-version
- [ ] Install mosh as alternative of ssh
- [ ] One-parameter group for every possible (web,cache,db,queue)
- [ ] Send report via e-mail
  - [ ] Hide report at the end
  - [ ] Hide more our warning/info/success
  - [ ] Run quiet installation with minimum verbosity
  - [ ] Reboot after done
- [ ] Count time passed during installation

## Contributing
You are welcome, just do a PR with some explanation.

## License
> Licensed under GNU LESSER GENERAL PUBLIC LICENSE. Check the [GNU GPL3 License](./LICENSE) file for more details.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk5NjMyNDMwNywtODY2ODEyMjQzLC05OT
YzMjQzMDddfQ==
-->