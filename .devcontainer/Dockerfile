# latest swift on ubuntu
FROM swift:6.1.2-noble

# Install CMake 3.29, which isn't available in the default repository.
RUN apt-get update && \
    apt-get install -y --no-install-recommends wget software-properties-common gpg-agent && \
    wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | gpg --dearmor - | tee /usr/share/keyrings/kitware-archive-keyring.gpg >/dev/null && \
    echo "deb [signed-by=/usr/share/keyrings/kitware-archive-keyring.gpg] https://apt.kitware.com/ubuntu/ $(. /etc/os-release && echo $VERSION_CODENAME) main" | tee /etc/apt/sources.list.d/kitware.list && \
    apt-get update && \
    apt-get install -y --no-install-recommends cmake ninja-build && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
