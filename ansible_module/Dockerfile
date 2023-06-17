FROM centos:7

USER root

RUN yum install -y epel-release 

RUN yum install -y ansible zlib zlib-devel openssl-devel wget sudo

RUN yum groupinstall -y "Development Tools" $$ yum clean all

WORKDIR "/usr/src"

RUN wget https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.1.tar.gz --no-check-certificate \
&& tar -xzvf ruby-2.6.1.tar.gz \
&& rm -f /usr/src/ruby-2.6.1.tar.gz

WORKDIR "/usr/src/ruby-*"

RUN /usr/src/ruby-*/configure && make && make install

RUN gem update --system 3.2.3 && gem install bundler 

COPY systemctl.py /usr/bin/systemctl
RUN sed -i -e 's/\r$//' /usr/bin/systemctl
RUN chmod a+x /usr/bin/systemctl     