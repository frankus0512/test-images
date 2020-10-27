# init from ubuntu:xenial for compatibility
FROM ubuntu:xenial

# prereqs
RUN apt-get update
RUN apt-get install -y wget build-essential libssl-dev opensc uuid-runtime

# Must be provided during build-time
ARG VERSION

# deploy softhsm
WORKDIR /app
RUN wget https://dist.opendnssec.org/source/softhsm-${VERSION}.tar.gz
RUN tar xvf softhsm-${VERSION}.tar.gz
WORKDIR /app/softhsm-${VERSION}
RUN ./configure
RUN make
RUN make install
