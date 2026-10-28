FROM python:3.10-slim

# Instalar dependencias del sistema si las necesitas (como Java si ANTLR lo requiere)
RUN apt-get update && apt-get install -y default-jre && rm -rf /var/lib/apt-get/lists/*

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 5000

CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app"]