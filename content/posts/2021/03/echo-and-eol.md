---
title: "echo 与 eol"
date: 2021-03-12T13:20:24+08:00
tags: ["shell"]
draft: false
---

echo 在默认情况下会在输出后加[换行符（LF）](https://zh.wikipedia.org/wiki/換行)。在终端中使用时可以让 shell 的提示符在 echo 输出的下一行正常显示，但在脚本中使用就可能带来意想不到的问题。

比如下面这个脚本：
```bash
#!/usr/bin/bash
echo password | sha3sum --algorithm 512 -
```

echo 实际向管道输出的字符为 ```password\n```，这就导致最后得到的散列和与预期不符。

可以使用 ```-n``` 参数使 echo 只输出命令行参数，进而避免这个问题。
