FROM oven/bun:latest AS build

WORKDIR /app

COPY package.json ./
COPY apps ./apps
COPY packages ./packages

RUN bun install
RUN bun --filter backend run build

FROM oven/bun:latest
WORKDIR /app
COPY --from=build /app/apps/backend/dist ./dist
EXPOSE 9000
CMD ["bun", "--filter", "backend", "run", "start:prod"]
