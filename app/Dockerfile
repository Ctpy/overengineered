FROM node:18-alpine AS base
FROM base AS deps
# Check https://github.com/nodejs/docker-node/tree/b4117f9333da4138b03a546ec926ef50a31506c3#nodealpine to understand why libc6-compat might be needed.
RUN apk add --no-cache libc6-compat


WORKDIR /app
COPY . .

RUN npm install
RUN npm -g install next

# ENV NODE_ENV production
ENV NEXT_TELEMETRY_DISABLED 1

CMD ["npm", "run", "dev"]
