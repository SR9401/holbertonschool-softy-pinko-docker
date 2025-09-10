FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

# MAJ + install Python et pip
RUN apt-get update \
 && apt-get upgrade -y \
 && apt-get install -y python3 python3-pip \
 && rm -rf /var/lib/apt/lists/*

RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED

# Installer Flask via pip3
RUN pip3 install --no-cache-dir flask

RUN pip3 install flask-cors

# Dossier de travail
WORKDIR /app

# Copier l’app
COPY api.py /app/api.py

# Exposer le port
EXPOSE 5252

# Lancer le serveur
CMD ["python3", "api.py"]
