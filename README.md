# MiMa.html
password-manager in one html file


## v1.1 bugfix (update: 2017-02-19)

在 Advanced Mode, 删除功能有 **严重bug** 导致不想删除的项目也会被删除。已修复，请使用最新版本。

## v1.1 (update: 2017-01-24)

新增了 Advanced Mode, 进入此模式后，可以更改主密码、顶置项目（或取消顶置）、删除项目。

Advanced Mode 采用了类似 TiddlyWiki 的方式，自动生成新文件，用户无需操作源代码。

一切修改都必须保存后才有效，点击 Save 时，会下载一个新文件，之后请使用这个新文件，删除旧文件。


## v1.0 说明：

这是一个密码管理软件，只有一个 HTML 文件，无任何外部依赖或链接。支持 Firefox 和 Chrome，不支持
IE 和 Edge，没有测试 Safari。

使用了 Stanford Javascript Crypto Library 和 jQuery, 我把它们整个儿复制粘贴到 HTML 文件
里了，因此整个程序只有一个文件（也不大，100KB多点），管理、使用、备份都非常方便。

源代码非常简单、清晰，有什么用着不爽的地方用户可以自己修改。

使用时，需要把 MiMa.html 下载到本地，用 Firefox 或 Chrome 打开，即可使用。

###创建条目

在创建条目的表格里填写资料后，点击 Encrypt 按钮即可生成密文，点击密文的文本框会自动复制
到剪贴板，**然后，需要手动粘贴到源文件里**，保存，刷新一下页面或下次打开文件时，就可以看到新建的条目。

> 源文件的开头部分有一句 `/****** PASTE CIPHERTEXT HERE ******/`，密文粘贴在这句下面。

###关于搜索

由于是 HTML 文件，因此直接在页面上按 Ctrl+F 即可进行全文搜索。此时，如果在搜索内容的开头
加上 t:，比如 `t:163` 就可以只搜索以163开头的条目标题，不会搜索用163邮箱做用户名的条目，使搜索
结果更精确。

每个条目里的用户名、密码的文本框，点击一下就可以自动复制到剪贴板，不需要 Ctrl+C。

###关于删除

和创建条目一样，需要手动在源代码里删除。每个条目都有 Ciphertext，点击一下文本框就会自动复制到剪贴板，
然后在源代码里搜索，就能找到，删除，保存。刷新一下页面或下次打开文件时，就可以看到相应的条目已经被删除了。

###关于修改

无法直接修改，只能通过删除旧条目和创建新条目来修改。把单个条目的 Ciphertext 复制粘贴到创建新条目的
那个表格的 Ciphertext 文本框里，点击 Decrypt 按钮，即可把旧内容自动填写到表格里，修改后点击 
Encrypt 按钮生成新的密文。由于这只是一个 HTML 文件而已，也只能这样尽可能提供方便了。

###关于安全

使用 AES 加密方法，对于不涉及大额金钱的账号来说，安全性完全足够了（当然，主密码必须是强密码）。由于
直接给出了密文，因此就算以后本软件或者 Stanford Javascript Crypto 不更新，也可以使用其他 AES
软件来解密，不用担心失去软件支持。

在使用过程中，可以通过控制台查看主密码，存在主密码泄漏的风险，因此，离开电脑的时候要记得点击 Safe Exit
按钮或关闭页面。另外，页面本身也有一个倒计时，30分钟后会自动安全退出。

复制密码后，密码会留在剪贴板里，需要用户自己复制一些别的东西来覆盖掉，建议先复制粘贴密码，后复制粘贴
用户名，即可解决这个问题。

###修改主密码

暂时没有这个功能，以后增加。(在 v1.1 中有此功能)
