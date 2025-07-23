FROM python:3.11

WORKDIR /app

# Copia tudo dentro da pasta 'backend'
COPY . .

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

CMD ["uvicorn", "core.asgi:application", "--host", "0.0.0.0", "--port", "8000"]
