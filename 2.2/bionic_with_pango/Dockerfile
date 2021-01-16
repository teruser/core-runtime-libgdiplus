FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-bionic
RUN apt-get update \
    && apt-get install -y --no-install-recommends libpango1.0-dev libc6-dev \
     libgif-dev git autoconf libtool automake build-essential gettext libglib2.0-dev libcairo2-dev libtiff-dev libexif-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN git clone https://github.com/mono/libgdiplus
WORKDIR /libgdiplus
RUN ./autogen.sh --with-pango
RUN make
RUN make install
RUN ln -s /usr/local/lib/libgdiplus.so /usr/lib/libgdiplus.so