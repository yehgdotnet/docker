#
# THIS FILE IS AUTOGENERATED; SEE "contrib/builder/rpm/amd64/generate.sh"!
#

FROM centos:6

RUN rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org
RUN yum install -y http://www.elrepo.org/elrepo-release-6-6.el6.elrepo.noarch.rpm
RUN yum install -y --enablerepo=elrepo-kernel kernel-lt-headers

RUN yum groupinstall -y "Development Tools"
RUN yum install -y  device-mapper-devel glibc-static  libselinux-devel libtool-ltdl-devel pkgconfig selinux-policy selinux-policy-devel sqlite-devel systemd-devel tar git

ENV GO_VERSION 1.6.3
RUN curl -fSL "https://storage.googleapis.com/golang/go${GO_VERSION}.linux-amd64.tar.gz" | tar xzC /usr/local
ENV PATH $PATH:/usr/local/go/bin

ENV AUTO_GOPATH 1

ENV DOCKER_BUILDTAGS exclude_graphdriver_btrfs pkcs11 selinux
ENV RUNC_BUILDTAGS selinux

