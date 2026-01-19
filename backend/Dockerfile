FROM python:3.12-slim AS base

FROM base

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /app

RUN adduser --disabled-password --gecos "" appuser

COPY app.py /app/app.py

EXPOSE 8080

USER appuser

CMD ["python", "/app/app.py"]
