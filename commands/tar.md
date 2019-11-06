# tar 

## 基本用法

加密并压缩

```bash
tar -zcvf - FILENAME | openssl des3 -salt -k PASSWORD -out FILENAME.tar.gz
```

解密并解压缩

```bash
openssl des3 -d -salt -k PASSWORD -in FILENAME.tar.gz | tar -zxvf -
```
