# CloudFoundry installation Guide

## install BOSH  CLI

```
### SSH into BOSH CLI machine.
$ sudo -i
$ apt-get update
$ sudo apt-get install build-essential ruby ruby-dev libxml2-dev libsqlite3-dev libxslt1-dev libpq-dev libmysqlclient-dev zlib1g-dev
$ gem install bosh_cli --version 1.3022.0 --no-ri --no-rdoc
$ gem install bosh_cli_plugin_micro --version 1.3022.0 --no-ri --no-rdoc
```

## Deploy MicroBOSH to AWS
```
$ mkdir -p ~/dir-installation/micro-deployment
$ cd dir-installation/micro-deployment
### create microbosh manifest file.
$ vi microbosh.yml
### copy keypair into BOSH CLI machine. Chmod 600.
$ chmod 600 dir-bosh.pem
### Download Stemcell
$ mkdir -p ~/dir-installation/stemcells
$ cd -p ~/dir-installation/stemcells
$ wget https://s3.amazonaws.com/bosh-jenkins-artifacts/bosh-stemcell/aws/bosh-stemcell-2989-aws-xen-ubuntu-trusty-go_agent.tgz
### Deploy microBOSH instance
$ bosh micro deployment ~/dir-installation/micro-deployment/microbosh.yml
$ bosh micro deploy ~/dir-installation/stemcells/bosh-stemcell-2989-aws-xen-ubuntu-trusty-go_agent.tgz

```
## Deploy CloudFOundry jobs to AWS
```

```
