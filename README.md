# Gitea package for YunoHost

Gitea is a fork of Gogs a self-hosted Git service written in Go. Alternative to Github.
- [Gitea website](http://gitea.io)

[![Integration level](https://dash.yunohost.org/integration/gitea.svg)](https://ci-apps.yunohost.org/jenkins/job/gitea%20%28Community%29/lastBuild/consoleFull) 

[![Install Gitea with YunoHost](https://install-app.yunohost.org/install-with-yunohost.png)](https://install-app.yunohost.org/?app=gitea)

![](https://gitea.io/images/screenshot.png)
## Requirements
A functional instance of [YunoHost](https://yunohost.org)

## Installation
From the command-line:

`sudo yunohost app install https://framagit.org/YunoHost-Apps/gitea_ynh`

## Upgrade
From the command-line:

`sudo yunohost app upgrade Gitea -u https://framagit.org/YunoHost-Apps/gitea_ynh gitea`

## Notes on SSH usage
If you want to use Gitea with ssh and be able to pull/push with you ssh key, your ssh daemon must be properly configured to use private/public keys. Here is a sample configuration of `/etc/ssh/sshd_config` that works with Gitea:

```bash
PubkeyAuthentication yes
AuthorizedKeysFile %h/.ssh/authorized_keys
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```

You also need to add your public key to your Gitea profile.

If you use ssh on another port than 22, you need to add theses lines to your ssh config in `~/.ssh/config`:

```bash
Host domain.tld
    port 2222 # change this with the port you use
```


Architecture: this package is compatible with amd64, i386 and arm. The package will try to detect it with the command uname -m and fail if it can't detect the architecture. If that happens please open an issue describing your hardware and the result of the command `uname -m`.

## Issue

Any issue is welcome here : https://framagit.org/YunoHost-Apps/gitea_ynh/issues

## License
Gitea is published under the MIT License:
https://github.com/go-gitea/gitea/blob/master/LICENSE

This package is published under the MIT License.
