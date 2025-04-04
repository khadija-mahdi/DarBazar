FROM debian:bullseye

# Update and install required packages
RUN apt-get -y update && \
    apt-get install nginx -y && \
    apt-get install openssl -y && \
    apt-get install curl -y

# Create directories for SSL certificates
RUN mkdir -p /etc/ssl/certs/ && \
    mkdir -p /etc/ssl/private

# # Copy the certs from the build context
# COPY /etc/letsencrypt/live/gosimple.ma/fullchain.pem /etc/ssl/certs/fullchain.pem
# COPY /etc/letsencrypt/live/gosimple.ma/privkey.pem /etc/ssl/private/privkey.pem

# Copy your custom nginx configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose necessary ports
EXPOSE 80
EXPOSE 443

# Start nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
