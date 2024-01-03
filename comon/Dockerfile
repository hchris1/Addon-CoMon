ARG BUILD_FROM
ARG COMON_VERSION
FROM hchris1234/comon:$COMON_VERSION as comon
FROM $BUILD_FROM

# Install dependencies for ping and dotnet
RUN apk add iputils-ping icu-libs

# Copy application
COPY --from=comon /app /opt/comon

# Folder for persistent data
RUN mkdir /data

# Copy root filesystem
COPY rootfs /