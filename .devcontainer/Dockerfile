FROM qmcgaw/godevcontainer:debian

RUN apt-get -qq update && \
    apt-get -qq install -y curl bash zip

# Install air
COPY --from=cosmtrek/air:latest /go/bin/air /go/bin/air

# Remove existing Go installation
RUN rm -rf /usr/local/go

# Clean up any cached files
RUN rm -rf /root/.cache/go-build

# Install lts go version
RUN curl -fsSL https://go.dev/dl/go1.24.2.linux-amd64.tar.gz | \
    tar -C /usr/local -xzvf -


VOLUME /workspace
WORKDIR /workspace
