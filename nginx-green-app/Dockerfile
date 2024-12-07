# Use the official Nginx image from the Docker Hub
FROM nginx:alpine

# Set the maintainer label (optional)
LABEL maintainer="your-email@example.com"

# Copy the local content (your /green directory) into the container
# The root directory for Nginx is /usr/share/nginx/html
COPY ./green /usr/share/nginx/html/green

# Replace the default nginx.conf with your custom configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Expose the port Nginx is running on (80)
EXPOSE 80

# Start Nginx when the container runs
CMD ["nginx", "-g", "daemon off;"]
