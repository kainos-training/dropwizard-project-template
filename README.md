#Template Project
This project is designed primarily for training purposes. I will be use to quickly spin up a target environment for small projects using play as the base framework.

## Contents
- Play sample application
- Jenkins build server

## Prerequists
- [Vagrant](vagrantup.com)
- [VirualBox](https://www.virtualbox.org/)

## Run
```bash
git clone git@github.com:andrew-js-wright/project-template.git
cd project-template
vagrant up
```

## View jenkins configuration
Navigate to the following location in your web browser.
```bash
localhost:8080
```
By default jenkins will poll a predefined git repository, check out the repo into a local working directory and build it using SBT. 
It then moves the generated JAR into a location which is pointed to by the `sample-app` upstart configuration.

## View running application
Navigate to the following location in your web broswer
```bash
localhost:9000
```

## Run on AWS
In order to run on AWS run the following:

```
git checkout aws-setup
vagrant plugin install vagrant-aws
vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box

export AWS_KEY='your-key'
export AWS_SECRET='your-secret'
export AWS_KEYNAME='your-keyname'
export AWS_KEYPATH='your-keypath'

vagrant up
```

> You will need to create a new security group on your AWS account to forward the correct ports - in particular SSH should be open. Then reference this group in the Vagrantfile.
