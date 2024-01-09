# Use a multi-stage build to support multiple architectures
# This is a generic Dockerfile and may need to be adjusted for each service

# Builder stage
FROM --platform=$BUILDPLATFORM node:14 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Final stage
FROM --platform=$TARGETPLATFORM node:14
WORKDIR /app
COPY --from=builder /app/build ./build
COPY --from=builder /app/node_modules ./node_modules
CMD ["npm", "start"]