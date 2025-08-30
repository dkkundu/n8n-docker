# Use lightweight Node image
FROM node:18-alpine

# Set environment
ENV NODE_ENV=production
ENV N8N_PORT=5678

# Install tini (to handle process signals properly)
RUN apk add --no-cache tini

# Set workdir
WORKDIR /data

# Install n8n
RUN npm install -g n8n

# Expose default n8n port
EXPOSE 5678

# Run with tini
ENTRYPOINT ["/sbin/tini", "--"]
CMD ["n8n", "start"]
