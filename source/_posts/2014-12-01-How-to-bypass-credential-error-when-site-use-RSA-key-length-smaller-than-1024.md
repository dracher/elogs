title: How to bypass credential error when site use RSA key length smaller than 1024
date: 2014-12-01 10:41:59
tags: [windows, ie]
thumbnail: /img/blog.png
---

- [Microsoft 安全公告：最小证书密钥长度更新](http://support.microsoft.com/kb/2661254)

## Steps

- Open the terminal

```
certutil -setreg chain\minRSAPubKeyBitLength 512
```

- Open the site, import the credential into the `trust root credential zone`

- Add the site address into the `compatibility-view list`