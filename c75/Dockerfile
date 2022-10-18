FROM daocloud.io/library/centos:centos7.5.1804

MAINTAINER "qc" <17852657226@163.com>

ENV container docker

RUN mkdir /etc/yum.repos.d/bak \
    mv /etc/yum.repos.d/* /etc/yum.repos.d/bak; \
    curl -o /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo; \
    sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentOS-Base.repo; \
    sed -i 's/http/&s/' /etc/yum.repos.d/CentOS-Base.repo; \
    sed -i 's/gpgcheck=1/gpgcheck=0/' /etc/yum.repos.d/CentOS-Base.repo/etc/yum.repos.d/CentOS-Base.repo; \
    yum clean all;yum makecache;

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
     rm -f /lib/systemd/system/multi-user.target.wants/*; \
     rm -f /etc/systemd/system/*.wants/*; \
     rm -f /lib/systemd/system/local-fs.target.wants/*; \
     rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
     rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
     rm -f /lib/systemd/system/basic.target.wants/*; \
     rm -f /lib/systemd/system/anaconda.target.wants/*;

CMD ["/usr/sbin/init"]
