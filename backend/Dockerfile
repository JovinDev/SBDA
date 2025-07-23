FROM python:3.11

# Define diretório de trabalho
WORKDIR /app

# Copia o restante do projeto
COPY backend/ .

# Instala as dependências
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Expõe a porta padrão
EXPOSE 8000

# Usa o servidor ASGI correto
CMD ["uvicorn", "core.asgi:application", "--host", "0.0.0.0", "--port", "8000"]