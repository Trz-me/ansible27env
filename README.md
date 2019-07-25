# Ansible 2.7 Study/Test Environment powered by Ansible and Vagrant. 

## Required software before setting up:
- Ansible - (`yum install ansible` or `brew install ansible`)
- Python - (`yum install python`or `brew install python`)
- [Vagrant](https://www.vagrantup.com/downloads.html) - (`brew cask install vagrant`)
- [Virtualbox](https://www.virtualbox.org/wiki/Downloads) (`brew cask install VirtualBox`)
- SSHPASS `brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb`
### Install at once with the command below:
(`brew install ansible ; brew install python ; brew cask install vagrant ; brew cask install VirtualBox ; brew install https://raw.githubusercontent.com/kadwanev/bigboybrew/master/Library/Formula/sshpass.rb`)

If you're using a Mac, Gatekeeper will block virtualbox from installing. All you have to do is go to System Preferences and click Allow under the General tab and rerun installation.

## Set Up Instructions
1. Create a seperate `~/bin` directory and `cd` to it. 
2. Clone the environment repo to it with `git clone https://github.com/rdbreak/ansibleenv.git`
3. Change to the `ansibleenv` directory that is now in your `~/bin` directory.
3. Run `vagrant up --provider virtualbox` to deploy the environment _(You must be in the directory you cloned the repo to in order to run vagrant commands.)_

*Also, don't be spooked by any red font during the setup process. It won't have an affect on your exam environment.* 

_NOTE - You can use the VirtualBox console to interact with the VMs or through a terminal. If you need to reset the root password, you would need to use the console though._

The first time you run the vagrant up command, it will download the OS images for later use. In other words, it will take longest the first time around but will be faster when it is deployed again. You can run `vagrant destroy -f` to destroy your environment at anytime. **This will erase everything**. This environment is meant to be reuseable, If you run the `vagrant up --provider virtualbox` command after destroying the environment, the OS image will already be downloaded and environment will deploy faster. Everything should be provided that you would normally need during an actual exam. Hope this helps in your studies!

### It includes three systems:
- control.node.example.com
- ans1.node.example.com
- ans2.node.example.com

### Network Details:
###### control
192.168.55.80
###### node1
192.168.55.81
###### node2
192.168.55.82

### Accessing the systems
Remember to add the IP addresses to your local host file if you want to connect to the guest systems with the hostname.
Username - user
Password - password
- For root - use `sudo` or `sudo su`
Access example - `ssh user@192.168.55.81`

## Help
If you're having problems with the environment, please submit an issue by going to the `ISSUES` tab at the top. If you have more questions, looking for practice exams to use against this environment, or just looking for a fantastic Red Hat community to join, please navigate to #practiceexam in the [Red Hat Certs Slack Workspace](https://join.slack.com/t/redhat-certs/shared_invite/enQtNjAxNDc3MzYyMTAxLWZlM2ZhMGRlNGI2YjQyMzQ4NWEyNDIyYTJiNzcxM2E1ZDVkZmQ4MzU2MTc0ZDRlNzg2MTU5NWIwZjFjZDdjMGE).
