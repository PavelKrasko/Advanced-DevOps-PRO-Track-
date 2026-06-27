FROM python:3.11-slim-bookworm

WORKDIR /app

RUN --mount=type=secret,id=pip_config,target=/root/.pip/pip.conf \
    pip install flask

CMD ["python", "--version"]