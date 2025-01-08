# ------------ Nginx ------------
FROM nginx:1.27.3-alpine
# Install additional applications and packages
RUN apk add --no-cache bash vim busybox-extras bind-tools
# Copy the Nginx config 
COPY default.conf /etc/nginx/conf.d/default.conf
# Grant permission on files and directories for the Nginx user
RUN chown -R nginx:nginx /etc/nginx/ && \
    chown -R nginx:nginx /var/cache/nginx  && \
    touch /run/nginx.pid  && \
    chown -R nginx:nginx /run/nginx.pid  && \
    chown -R nginx:nginx /var/log/nginx  && \
    chown -R nginx:nginx /usr/share/nginx
# Create the default user
USER nginx
# Expose the Nginx port
EXPOSE 8080
