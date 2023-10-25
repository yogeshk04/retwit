#FROM nginx:1.23.2-alpine
#COPY nginx.conf /etc/nginx/nginx.conf

# Build Stage
FROM node:19-alpine3.15 AS build
WORKDIR /app
COPY package*.json /app/
RUN npm install
RUN npm install -g @angular/cli@14.0.1
COPY ./ /app/
RUN ng build --configuration production


# Run Stage
FROM nginx:1.23.2-alpine
COPY default.conf /etc/nginx/conf.d/default.conf
# COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist/frontend /usr/share/nginx/html