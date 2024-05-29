# Utiliser une image de base officielle de Python
FROM python:3.9-slim

# Installer les dépendances système nécessaires
RUN apt-get update && apt-get install -y \
    libpq-dev \
    gcc \
    && rm -rf /var/lib/apt/lists/*

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers requirements.txt et installer les dépendances
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Copier le contenu de l'application dans le répertoire de travail
COPY . .

# Définir le répertoire de travail où se trouve manage.py
WORKDIR /app/mysite

# Exposer le port sur lequel l'application fonctionnera
EXPOSE 8000

# Commande pour lancer l'application
CMD ["python", "manage.py", "spiritinstall", "0.0.0.0:8000"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
