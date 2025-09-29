# IND-python-dev-container
## Prerequisites
1. A running docker environment. This one is tested on a rancher desktop environment on MacOS 26.
```shell
% docker context ls
NAME                DESCRIPTION                               DOCKER ENDPOINT                           ERROR
...            
rancher-desktop *   Rancher Desktop moby context              unix:///Users/<username>/.rd/docker.sock
```
2. VS Code.
3. Clone `https://github.com/JoshData/convert-outlook-msg-file` into `˜/Development/convert-outlook-msg-file`. If you clone into another directory, adapt the `"mounts"` lines in [`devcontainer.json`](devcontainer.json) accordingly. This `README.md` was tested with commit [d9d8df7b4f4afe8aae60d707e58b72ac476d9d85](`https://github.com/JoshData/convert-outlook-msg-file/commit/d9d8df7b4f4afe8aae60d707e58b72ac476d9d85`).

## Run
In vs studio code run *Command Palette* - *Dev Containers: Rebuild Container*. In the terminal that was created you can run
```
$ python ../convert-outlook-msg-file/outlookmsgfile.py testOut_noattach.msg
```
to create the [`testOut_noattach.msg.eml`](testOut_noattach.msg.eml) file.

```bash
$ cat testOut_noattach.msg.eml
From: "peterpan@neverland.com" <>
To: crocodile@neverland.com
CC: =?utf-8?b?44i344i2AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA?=
BCC: =?utf-8?b?44i344i2AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA?=
Subject: This is the subject
Content-Type: text/plain; charset="utf-8"
Content-Transfer-Encoding: quoted-printable
MIME-Version: 1.0

=E3=88=B7=E3=88=B6=00=00=00=00=00=00=00=00=00=00=00=00=00=00=00=00=00=00=00=
=00=00=00=00=00=00=00=00=00=00=00
```

