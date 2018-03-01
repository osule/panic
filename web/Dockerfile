FROM python:3.6-slim

COPY . .
EXPOSE 5000

RUN apt-get update \
    && apt-get install -y gcc \
    && rm -rf /var/lib/apt/lists/* \
    && pip3 install sanic gunicorn

CMD gunicorn -b 0.0.0.0:5000 app:app --worker-class sanic.worker.GunicornWorker