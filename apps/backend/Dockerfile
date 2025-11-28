FROM oven/bun:1

WORKDIR /app

COPY . .

RUN bun install

WORKDIR /app/apps/backend

CMD ["bun", "run", "start:dev"]
