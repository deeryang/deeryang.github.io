---
title : scrapy安装
tags  : [python, 爬虫]
categories: python
---

scrapy是爬虫最常用的框架，下面记录安装使用scrapy时遇到的错误。

<!--more-->

在win10系统中，首先安装了Anaconda，但是并没有安装scrapy。需要我们自己安装。在命令行中输入`conda install scrapy`便会自行安装。
在开始爬取之前，需要先创建一个新的scrapy项目。
进入打算存储的目录中，在命令行中输入：

```bash
scrapy startproject spidername
```

此时会出现以下错误

```bash
D:\Work\Python\scrapy>scrapy startproject tutorial1
Traceback (most recent call last):
  File "d:\programfiles\anaconda3\lib\runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "d:\programfiles\anaconda3\lib\runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "D:\ProgramFiles\Anaconda3\Scripts\scrapy.exe\__main__.py", line 9, in <module>
  File "d:\programfiles\anaconda3\lib\site-packages\scrapy\cmdline.py", line 149, in execute
    cmd.crawler_process = CrawlerProcess(settings)
  File "d:\programfiles\anaconda3\lib\site-packages\scrapy\crawler.py", line 252, in __init__
    log_scrapy_info(self.settings)
  File "d:\programfiles\anaconda3\lib\site-packages\scrapy\utils\log.py", line 149, in log_scrapy_info
    for name, version in scrapy_components_versions()
  File "d:\programfiles\anaconda3\lib\site-packages\scrapy\utils\versions.py", line 35, in scrapy_components_versions
    ("pyOpenSSL", _get_openssl_version()),
  File "d:\programfiles\anaconda3\lib\site-packages\scrapy\utils\versions.py", line 43, in _get_openssl_version
    import OpenSSL
  File "d:\programfiles\anaconda3\lib\site-packages\OpenSSL\__init__.py", line 8, in <module>
    from OpenSSL import crypto, SSL
  File "d:\programfiles\anaconda3\lib\site-packages\OpenSSL\crypto.py", line 16, in <module>
    from OpenSSL._util import (
  File "d:\programfiles\anaconda3\lib\site-packages\OpenSSL\_util.py", line 6, in <module>
    from cryptography.hazmat.bindings.openssl.binding import Binding
  File "d:\programfiles\anaconda3\lib\site-packages\cryptography\hazmat\bindings\openssl\binding.py", line 13, in <module>
    from cryptography.hazmat.bindings._openssl import ffi, lib
ImportError: DLL load failed: 操作系统无法运行 %1。

```
![bug1](/images/05/bug1.png)

- 解决方法

```bash
pip install -I cryptography
```