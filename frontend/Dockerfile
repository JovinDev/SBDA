FROM node:20-alpine AS builder

WORKDIR /app
COPY app/package*.json ./app/
WORKDIR /app/app
RUN npm install

COPY app ./app
RUN npm run build  # <- ESSENCIAL

FROM node:20-alpine AS runner
WORKDIR /app/app

COPY --from=builder /app/app/.next ./.next
COPY --from=builder /app/app/node_modules ./node_modules
COPY --from=builder /app/app/public ./public
COPY --from=builder /app/app/package.json ./package.json

EXPOSE 3000
CMD ["npm", "start"]