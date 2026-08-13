FROM node:20-alpine

WORKDIR /app

COPY package.json package-lock.json* ./
RUN npm install --omit=dev

COPY . .

ENV NODE_ENV=production
EXPOSE 4000

# All secrets (DATABASE_URL, ADMIN_PASSWORD_HASH, SERVER_HMAC_SECRET) are
# injected at runtime via environment variables / your host's secret manager.
# Never bake them into the image.
CMD ["node", "src/index.js"]
