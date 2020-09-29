---
title: "Ways of Copying Files"
date: 2020-09-12T22:18:07+12:00
comments: true
tags:
  - linux
  - ssh
  - docker
---

Finding myself to google about this everytime.

![https://xkcd.com/1168/](/images/googling-skill.png "I have to google")

### 1. Copy file using SSH
```bash
# download
$ scp user@server.address:/path/to/input/file /path/to/output/folder
```
```bash
# upload
$ scp /path/to/input/file user@server.address:/path/to/output/folder
```

### 2. Copy file to/from Docker
```bash
# download
$ docker cp dockerhostname:/path/to/input/file /path/to/output/file
```
```bash
# upload
$ docker cp /path/to/input/file dockerhostname:/path/to/output/file
```