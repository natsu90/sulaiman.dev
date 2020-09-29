---
title: "Running Multiple Libreoffice Process"
date: 2020-09-12T22:19:44+12:00
comments: true
tags:
  - linux
  - msoffice
  - pdf
---

`LibreOffice` tool can be used to convert MSOffice documents to pdf file.

My team noticed that our system seems failed to convert the documents randomly after we are trying to run the process in parallel.

Digging up the internet, I found that it is a common issue, https://bugs.documentfoundation.org/show_bug.cgi?id=37531.

Fortunately there is a simple solution to that, by simply passing an additional parameter, to specify a different installation folder.

```bash
lowriter -env:UserInstallation=file://$random_dir --convert-to pdf --outdir $output_dir $input_file
```

> I am adding `-env:UserInstallation` parameter additionally from our existing command. The random folder as the name implied is a random string with absolute path, and the folder will be created automatically and do not need to be created beforehand.

#### Demo: https://github.com/natsu90/libreoffice-test