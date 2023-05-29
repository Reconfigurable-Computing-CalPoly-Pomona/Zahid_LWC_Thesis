# Stage 1: Build the client binary
FROM alpine:latest AS builder

# Set the working directory
WORKDIR /app
#COPY folder /app/folder
# Copy the source files
COPY client.c .
COPY x3dh_requirements /app/x3dh_requirements
#RUN ls -R
# Install the required packages
RUN apk add --no-cache build-base

# Compile the client binary
RUN gcc -o client client.c x3dh_requirements/microECC/uECC.c x3dh_requirements/opt32/aead.c x3dh_requirements/sha/rfc6234/*.c

# Stage 2: Create the final image
FROM alpine:latest

# Set the working directory
WORKDIR /app

# Copy the client binary from the builder stage
COPY --from=builder /app/client /app/client

# Set the entrypoint
ENTRYPOINT [ "./client" ]

#sudo docker build -t node_test:1.0.0 .
#sudo docker build . -t cpp_test:1.0.0
#Build: sudo docker build build_context -t name:version
#sudo docker tag clientkubersmall:1.0.1 mzahid22/clientkubersmall:1.0.1
#sudo docker push mzahid22/clientkubersmall:1.0.1

#docker buildx create --name multiarch-builder --driver docker-container --use
#docker buildx inspect multiarch-builder --bootstrap
#sudo docker buildx build --platform linux/amd64,linux/arm/v7,linux/arm64 -t mzahid22/clientkubersmallmultiarch:1.0.0 -f Dockerfile --push .
#docker buildx use multiarch-builder

#docker buildx use default
