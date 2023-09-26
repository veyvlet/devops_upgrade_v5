FROM centos:7

USER root

RUN yum install -y epel-release 

RUN yum install -y ansible wget sudo && yum clean all

COPY systemctl.py /usr/bin/systemctl
RUN sed -i -e 's/\r$//' /usr/bin/systemctl
RUN chmod a+x /usr/bin/systemctl     