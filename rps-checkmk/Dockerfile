FROM ubuntu:latest
RUN \
  apt-get update && \
  DEBIAN_FRONTEND=noninteractive \
    apt-get -y install --no-install-recommends \
      bc \
      bash \
      xinetd \
      check-mk-agent \
      python && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/

ADD check_mk /etc/xinetd.d/
ADD mrpe.cfg /etc/check_mk/
ADD speedtest /usr/local/bin/

RUN mkdir -p /usr/lib/check_mk_agent/local/600
ADD check_speedtest-cli.sh /var/lib/check_mk_agent/local/600/
RUN chmod +x /var/lib/check_mk_agent/local/600/check_speedtest-cli.sh && \
    chmod +x /usr/local/bin/speedtest

EXPOSE 6556

ENTRYPOINT [ "xinetd", "-dontfork" ]
