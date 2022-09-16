# 思源笔记 docker 搭建教程

## 1.🏷 env

* x86
* CentOS 7
* docker

## 2.🏷 deploy siyuan docker

```shell
mkdir -p /siyuan/workspace
chown -R 1000:1000 /siyuan/workspace
```

```shell
docker run -dit -v /siyuan/workspace:/siyuan/workspace \
                -p 6806:6806 \
                b3log/siyuan \
                -resident \
                -workspace /siyuan/workspace \
                -accessAuthCode 123456
```

## 3.🏷 open your browser, then access the URL

[http://ip:6806/](http://ip:6806/ "http://ip:6806/")

then, press accessAuthCode
