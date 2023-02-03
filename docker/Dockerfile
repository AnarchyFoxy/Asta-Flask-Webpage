FROM python:alpine AS builder

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /code
COPY requirements.txt /code/
RUN pip install -r requirements.txt

FROM builder AS runner

COPY . /code/
EXPOSE 2023

ENTRYPOINT ["gunicorn","--bind=0.0.0.0:2023","app:app"]