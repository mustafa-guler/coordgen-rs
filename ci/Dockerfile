FROM centos:8

RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN yum install -y gcc gcc-c++ make cmake
# RUN yum install cmake
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > install.sh
RUN sh install.sh -y
ENV PATH=/root/.cargo/bin:$PATH
WORKDIR app
COPY . .
CMD cargo test
