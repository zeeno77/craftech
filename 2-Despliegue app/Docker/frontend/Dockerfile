# Build React static files
# Current current-alpine
FROM node:16.10.0-alpine3.13 as build-stage

WORKDIR /app
COPY ./frontend/package.json .
COPY ./frontend/package-lock.json .
RUN npm ci --silent

COPY ./frontend .
RUN npm run build

# Copy React static files and start nginx
# Current stable-alpine
FROM nginx:1.20.1-alpine


#Copy builded project to nginx folder
COPY --from=build-stage assets/bundles /usr/share/nginx/html/static/public_bundles
#The project is broken so I copied the index to the root as a q&d fix
COPY --from=build-stage assets/bundles/index.html /usr/share/nginx/html/

CMD ["nginx", "-g", "daemon off;"]
