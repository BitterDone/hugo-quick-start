# Stage 1
FROM hugomods/hugo AS build

WORKDIR /src

# Copy Hugo config into the container Workdir.
COPY . .

# Run Hugo in the Workdir to generate HTML.
RUN hugo 

# Stage 2
FROM nginx:1.25-alpine

# Set workdir to the NGINX default dir.
WORKDIR /usr/share/nginx/html

# Copy HTML from previous build into the Workdir.
COPY --from=build /src/public .

# Expose port 80
EXPOSE 80/tcp

# docker build -t hugo-quick-start:0.0.1 .
