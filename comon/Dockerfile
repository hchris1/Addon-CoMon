ARG BUILD_FROM
ARG COMON_VERSION
FROM hchris1234/comon:$COMON_VERSION as comon
FROM $BUILD_FROM

# Install dependencies for ping and dotnet
RUN apk add iputils-ping icu-libs

# Copy application
COPY --from=comon /app /opt/comon

# Folder for persistent data to store db
RUN mkdir /data

# Copy root filesystem
COPY rootfs /

# Make scripts executable
RUN chmod a+x /etc/services.d/comon/run
RUN chmod a+x /etc/services.d/comon/finish