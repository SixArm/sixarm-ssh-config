# SixArm.com ➤ Secure Shell (SSH) ➤ ssh_config file


## Introduction

Our SSH configuration files are in two repos:

  * `sixarm-ssh-config` for the client configuration.

  * `sixarm-sshd-config` for the server configuration.

Take what you need. We welcome suggestions, feedback, and pull requests.


## Install


### For a typical user

Create your SSH directory as needed:

    mkdir -p ~/.ssh

Do you already have an SSH config file?

    ls ~/.ssh/config

If so, then you may want to make a backup:

    cp ~/.ssh/config ~/.ssh/config.backup

Clone:

    git clone https://github.com/sixarm/sixarm-ssh-config

Copy this repo file to your own SSH config file:

    cat sixarm-ssh-config/ssh_config >> ~/.ssh/config

Edit as you like, using your own favorite editor:

    edit ~/.ssh/config


### For all system users

Create your SSH directory as needed:

    mkdir -p /etc/ssh

Do you already have an SSH config file?

    ls /etc/ssh/ssh_config

If so, then you may want to make a backup:

    cp /etc/ssh/ssh_config /etc/ssh/ssh_config.backup

Clone:

    git clone https://github.com/sixarm/sixarm-ssh-config

Copy this repo file to your own SSH config file:

    cat sixarm-ssh-config/ssh_config >> /etc/ssh/ssh_config

Edit as you like, using your own favorite editor:

    edit /etc/ssh/ssh_config

## Help

For details about these settings:

```sh
man ssh_config
man sshd_config
```

Links to the man pages:

* <http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/ssh_config.5>

* <http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man5/sshd_config.5>


## Organization

SSH historically uses one config file.

We prefer to use many config files.

We like to organize our SSH config files by using directories:

    mkdir -p ~/.ssh/config.d

We copy the repo file to a filename that we know will sort first:

    cp ssh_config ~/.ssh/config.d/0.config

We create any subdirectories and any files:

    edit ~/.ssh/config.d/a/b/c.config
    edit ~/.ssh/config.d/x/y/z.config

Then we generate the main file by joining all the directory's files:

    find ~/.ssh/config.d -name '*.config' -exec cat {} \; > ~/.ssh/config


## Changes

* 2022-06-27 3.0.0 Rename repos
* 2016-04-03 2.0.0 Improve usability
* 2015-06-30 1.0.0 Publish


## License

You may choose any of these open source licenses:

  * Apache License
  * BSD License
  * CreativeCommons License, Non-commercial Share Alike
  * GNU General Public License Version 2 (GPL 2)
  * GNU Lesser General Public License (LGPL)
  * MIT License
  * Perl Artistic License
  * Ruby License

The software is provided "as is", without warranty of any kind,
express or implied, including but not limited to the warranties of
merchantability, fitness for a particular purpose and noninfringement.

In no event shall the authors or copyright holders be liable for any
claim, damages or other liability, whether in an action of contract,
tort or otherwise, arising from, out of or in connection with the
software or the use or other dealings in the software.

This license is for the included software that is created by SixArm;
some of the included software may have its own licenses, copyrights,
authors, etc. and these do take precedence over the SixArm license.

Copyright (c) 2015-Present Joel Parker Henderson
