FROM python:3.12-slim AS base

FROM base

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /app

RUN adduser --disabled-password --gecos "" appuser

COPY app.py /app/app.py

EXPOSE 8080

HEALTHCHECK --interval=10s --timeout=2s --retries=3 \
  CMD python -c "import urllib.request; urllib.request.urlopen('http://127.0.0.1:8080/', timeout=1).read()"

USER appuser

CMD ["python", "/app/app.py"]
