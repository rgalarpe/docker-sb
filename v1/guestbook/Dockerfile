FROM node:20-alpine

WORKDIR /app

# Copy pre-installed dependencies
COPY node_modules ./node_modules
COPY package*.json ./

# Copy application source
COPY server.js ./
COPY public ./public/

# Create non-root user
RUN addgroup -S nodejs && adduser -S nodeuser -G nodejs

RUN chown -R nodeuser:nodejs /app
USER nodeuser

EXPOSE 3000
CMD ["node", "server.js"]
