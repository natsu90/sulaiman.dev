---
title: "Handling Winmail Attachment"
date: 2020-09-12T22:19:05+12:00
comments: true
tags:
  - linux
  - email
---

Somehow you will receive an email contains with only `winmail.dat` attachment when it is sent from Microsoft Outlook client.

To handle this you will need [`TNEF`](https://linux.die.net/man/1/tnef) command to extract the content.

```bash
$ tnef --number-backups --save-body=filename_to_be --body-pref=H --directory=/path/to/output/folder /path/to/winmail/file 2>&1
```
> `--number-backups`; there could be some attachments with the same name, so this will put a digit at the end of each of duplicated files, otherwise it will be overwritten e.g. *file, file.1, file.2*

> `--save-body`; this will save the email body to a file with the specified filename; `filename_to_be`

> `--body-pref`; the email body could be in *(R)TF*, *(T)EXT*, or *(H)TML* format. But let's get only HTML format if any.