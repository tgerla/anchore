Anchore
=======

*See the wiki at https://github.com/anchore/anchore/wiki for more documentation.*

Anchore is a container inspection and analytics platform to enable
operators to deploy containers with confidence. The Anchore toolset in
this repository provides the ability to inspect, reason about, and
evaluate policy against containers present on the local Docker host.

To get started on CentOS 7 as root:

1) install docker (see docker documentation for CentOS 7 install instructions)

``https://docs.docker.com/engine/installation/linux/centos/``

2) install some packages that full functionality of anchore will require

``yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm``

``yum install python-pip graphviz rpm-python dpkg``

To get started on Ubuntu 15.10/16.04 as root:

1) install docker engine >= 1.10 (see docker documentation for Ubuntu 15.10/16.04 install instructions)

``https://docs.docker.com/engine/installation/linux/ubuntulinux/``

2) install some packages that full functionality of anchore will require

``apt-get install python-pip graphviz python-rpm yum``

Next, on either distro:

3) install Anchore to ~/.local/

``cd <where you checked out anchore>``

``pip install --upgrade --user .``

``export PATH=~/.local/bin:$PATH``

4) run anchore!  Here is a quick sequence of commands to help get going

``anchore --help``

``anchore sync catalog``

``anchore subscriptions show``

``anchore subscriptions add ubuntu centos ubuntu:quantal``

``anchore sync catalog``

``anchore explore report``

``anchore explore query has-package curl wget``

``anchore explore query cve-scan all``

For more information, to learn about how to analyze your own
application containers, and how to customize/extend Anchore, please
visit our github page wiki at https://github.com/anchore

Manual Pages
============
Man pages for most of the anchore commands are available in: $anchore/doc/man, where $anchore is the install
location of the python code for your distro (e.g. /usr/local/lib/python2.7/dist-packages/anchore for ubuntu).
To install them, copy them to the appropriate location for your distro. The man pages are generated from --help
and --extended-help options to anchore commands, so similar content is available direclty from the CLI as well.

