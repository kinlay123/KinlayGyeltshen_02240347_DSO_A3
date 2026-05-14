FROM node:22-alpine

WORKDIR /app

COPY package*.json ./
COPY prisma ./prisma
COPY prisma.config.ts ./
COPY tsconfig.json ./

RUN npm install
RUN npm install -g tsx

# Generate Prisma client (no DB needed for this step)
RUN npx --yes prisma@7.8.0 generate --config prisma.config.ts

COPY . .

EXPOSE 5000

CMD ["node", "server.js"]