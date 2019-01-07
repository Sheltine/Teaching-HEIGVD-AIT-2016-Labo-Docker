# Base image is the Official HAProxy
FROM haproxy:1.5

# TODO: [GEN] Replace with your name and email
MAINTAINER Johanna Melly <johanna.melly@heig-vd.ch> Yohann Meyer <yohann.meyer@heig-ch>

# Install some tools
# TODO: [HB] Update to install required tool to install NodeJS
RUN apt-get update && apt-get -y install wget curl vim iputils-ping rsyslog

# TODO: [S6] Install

# TODO: [Serf] Install

# TODO: [HB] Install NodeJS

# TODO: [HB] Install Handlebars

# TODO: [S6] Replace the two following instructions
# Copy all the scripts and make them executable
# Copy the S6 service and make the run script executable
COPY services/ha /etc/services.d/ha
RUN chmod +x /etc/services.d/ha/run

# TODO: [Serf] Add Serf S6 setup

# TODO: [Serf] Copy events handler scripts

# Copy the haproxy and syslog config
COPY config/haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
COPY config/rsyslogd.cfg /etc/rsyslog.d/49-haproxy.conf

# TODO: [HB] Copy the haproxy configuration template

# Clean up
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# TODO: [CFG] Create the nodes folder

# TODO: [Serf] Expose ports

# Expose the HA proxy ports
EXPOSE 80 1936

# Define an environment variable
ENV ROLE balancer

# TODO: [S6] Replace the following instruction
# Command executed when the container starts
CMD [ "/scripts/run.sh" ]
