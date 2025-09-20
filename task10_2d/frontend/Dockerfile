# Simple static frontend served by Nginx
FROM nginx:alpine

# Optional: use your custom nginx.conf if present
# (you already have nginx.conf in task10_2d/frontend)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Copy static assets (index.html, main.js, etc.)
COPY . /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
