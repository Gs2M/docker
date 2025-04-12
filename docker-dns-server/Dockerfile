# Use CentOS Stream 9 as the base image
FROM quay.io/centos/centos:stream9

# Install necessary packages
RUN dnf install -y \
    bind bind-utils vim net-tools hostname \
    && dnf groupinstall -y "Development Tools" \
    && dnf clean all

# Copy the BIND configuration files
COPY named.conf /etc/named.conf
COPY zones/ /var/named/

# Set correct permissions for BIND
RUN chown -R named:named /var/named \
        && chown named:named /etc/named.conf \
        && chmod 777 /etc/named.conf \
        && chmod 777 /var/named
        
EXPOSE 53/udp
EXPOSE 53/tcp
# Start the BIND service
CMD ["/bin/bash", "-c", "named -g & /bin/bash"]