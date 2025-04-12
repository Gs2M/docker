# Use CentOS Stream 9 as base image
FROM quay.io/centos/centos:stream9

# Install Apache HTTP server
RUN dnf install -y httpd && dnf clean all

# Copy the index.html to Apache's default web root
COPY index.html /var/www/html/index.html

# Expose default HTTP port
EXPOSE 80

# Start Apache in background and open an interactive shell
CMD ["/bin/bash", "-c", "/usr/sbin/httpd && exec /bin/bash"]