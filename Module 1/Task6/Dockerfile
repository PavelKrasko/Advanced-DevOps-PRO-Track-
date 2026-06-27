FROM python:3.11-slim-bookworm

WORKDIR /app

RUN --mount=type=cache,target=/root/.cache/pip \
    pip install flask

CMD ["python", "--version"]