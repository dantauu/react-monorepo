FROM oven/bun:latest AS build

WORKDIR /app

COPY package.json ./
COPY apps ./apps
COPY packages ./packages

RUN bun install
RUN bun --filter frontend run build

FROM nginx:alpine
COPY --from=build /app/apps/frontend/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
