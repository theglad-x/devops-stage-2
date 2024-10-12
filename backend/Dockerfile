FROM python:latest

RUN apt-get update && apt-get install -y nodejs npm

RUN pip install poetry

WORKDIR /app

COPY . .

RUN poetry install

EXPOSE 8000

CMD ["sh", "-c", "poetry run bash ./prestart.sh && poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload"]

