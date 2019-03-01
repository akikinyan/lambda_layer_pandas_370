# LambdaLayers pandas Python3.7.0

- EC2インスタンスを作成(AmazonLinux)してsshで入る
- pyenvを入れる
- pandasを入れる

## pyenvを入れる

Amazon Linux AMI 2018.03で作業を行います。
LambdaはAmazonLinuxで動いてるそうなので、Amazon Linux2ではありません。
AMIを選ぶときはぐれぐれもご注意ください。

```
$ sudo yum install -y gcc gcc-c++ make git openssl-devel bzip2-devel zlib-devel readline-devel sqlite-devel libffi-devel
$ git clone https://github.com/yyuu/pyenv.git ~/.pyenv
$ echo 'export PYENV_ROOT="${HOME}/.pyenv"' >> ~/.bashrc
$ echo 'if [ -d "${PYENV_ROOT}" ]; then' >> ~/.bashrc
$ echo 'export PATH=${PYENV_ROOT}/bin:$PATH' >> ~/.bashrc
$ echo 'eval "$(pyenv init -)"' >> ~/.bashrc
$ echo 'fi' >> ~/.bashrc
$ source ~/.bashrc
$ pyenv install --list|grep 3.7
$ pyenv install 3.7.0
$ pyenv global 3.7.0
$ python --version
$ pip --version
```


# pandasを入れる

```
$ mkdir python

$ pip install -t ./python pandas
$ zip -r pandas.zip python

$ ls -l
合計 34308
-rw-rw-r--  1 ec2-user ec2-user 35124856  3月  1 00:26 pandas.zip
drwxrwxr-x 13 ec2-user ec2-user     4096  3月  1 00:21 python
```

# 参考URL

https://qiita.com/thimi0412/items/4c725ec2b26aef59e5bd

