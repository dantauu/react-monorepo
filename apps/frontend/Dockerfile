FROM oven/bun:1

WORKDIR /app

COPY . .

RUN bun install

WORKDIR /app/apps/frontend

CMD ["bun", "x", "vite", "--host", "--port", "5137"]
