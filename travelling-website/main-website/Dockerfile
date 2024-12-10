# Stage 1: Build React app
FROM node:16 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Serve with Nginx
FROM nginx:latest
#Set environment variables (optional: default values can be overridden at runtime)
ENV GOA_API_URL="goa-service"
ENV RAJASTHAN_API_URL="rajasthan-service"
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
