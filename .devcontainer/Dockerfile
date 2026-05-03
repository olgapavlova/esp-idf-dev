# Официальный ESP-IDF образ.
# Версию лучше фиксировать, а не использовать latest.
FROM espressif/idf:v6.0.1

ARG USERNAME=ubuntu

# Инструменты для нормальной dev-среды и serial.
RUN apt-get update && apt-get install -y --no-install-recommends \
    bash \
    sudo \
    git \
    curl \
    wget \
    unzip \
    screen \
    picocom \
    usbutils \
    udev \
    jq \
    && rm -rf /var/lib/apt/lists/*

# Права на serial/USB и sudo без пароля.
RUN usermod -aG dialout,plugdev ${USERNAME} \
    && echo "${USERNAME} ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/${USERNAME} \
    && chmod 0440 /etc/sudoers.d/${USERNAME}

WORKDIR /workspace