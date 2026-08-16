# 1. Usar una imagen base con Python 3.7 sobre Debian Buster
FROM python:3.7-buster

# Variables de entorno para evitar prompts interactivos durante la instalación
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1

# ------------------------------------------------------------------
# INSTALACIONES COMO ROOT
# ------------------------------------------------------------------
USER root

# --- INICIO DE LA CORRECCIÓN ---
# Actualizar las fuentes de APT para apuntar al archivo de Debian
# Esto es NECESARIO porque Debian 10 "Buster" está en EOL (End-of-Life)
RUN sed -i 's/deb.debian.org/archive.debian.org/g' /etc/apt/sources.list && \
    sed -i 's|security.debian.org/debian-security|archive.debian.org/debian-security|g' /etc/apt/sources.list && \
    sed -i '/buster-updates/d' /etc/apt/sources.list

# Instalar dependencias del sistema, incluyendo las necesarias para geopandas
RUN apt-get update && apt-get install -y --no-install-recommends \
    # Herramientas generales
    jq \
    git \
    curl \
    nano \
    make \
    # Dependencias para paquetes de Python
    libzmq3-dev \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    libicu-dev \
    # Dependencias clave para librerías geoespaciales
    libgdal-dev \
    libgeos-dev \
    proj-bin \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Actualizar pip
RUN pip install --no-cache-dir --upgrade pip

# Copiar requerimientos históricos y constraints de compatibilidad Python 3.7
COPY requirements.txt /tmp/requirements.txt
COPY constraints-py37.txt /tmp/constraints-py37.txt

# Instalar los paquetes preservando los requerimientos históricos y
# limitando únicamente incompatibilidades transitivas verificadas.
RUN pip install --no-cache-dir \
        -c /tmp/constraints-py37.txt \
        -r /tmp/requirements.txt \
    && rm /tmp/requirements.txt /tmp/constraints-py37.txt

# Descargar el modelo de Spacy
RUN python -m spacy download es_core_news_sm

# Exponer el puerto para Jupyter
EXPOSE 8888

# El workspace y el ciclo de vida del contenedor son gestionados por VS Code Dev Containers.
