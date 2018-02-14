
# SSH HoneyPot

Great opportunity to check what attackers would act on your server.

## Getting Started

First of all, credit for part of code and the central idea goes to [bechampion](https://github.com/bechampion/honey) - where this project came from.
Here you will find automation for this deployment using scripts and Ansible. (I hope to use Ansible 100% soon).

## How it works

- Original SSH service was moved from default port (**22**) to another (configurable)
- A container (**Docker**) will be used for each connection on port **22** to keep attackers isolated and under control.
- Inside the container we have few commands available like *ls*, *ps*, wchi will produce fake results.
- Every command fired inside container will be logged, script *check_bee.sh* can be used to follow it up.
- Another script *clean_bee.sh* is responsible to delete containers older than 5 minutes

## Prerequisites

This solution was built under **CentOS** Linux, version 7.0 or higher and Kernel 3.8.x or above.

```
[honey@sshhoneypot ~]$ cat /etc/redhat-release 
CentOS Linux release 7.4.1708 (Core) 

[honey@sshhoneypot ~]$ uname -r
3.10.0-693.17.1.el7.x86_64
```

## Installing

I'd recommend first test using **Vagrant** to check it on your local environment.
```
vagrant up
```

If you are confident and ready to install on your "production", just trigger it.

```
./installMe.sh
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
