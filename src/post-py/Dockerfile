FROM python:3.6.0-alpine

WORKDIR /app
ADD . /app

RUN apk update && apk add build-base && apk add musl-dev && rm -rf /var/cache/apk/*
RUN pip install -r /app/requirements.txt --no-cache-dir && rm -Rf ~/.cache/pip

ENV POST_DATABASE_HOST post_db
ENV POST_DATABASE posts

ENTRYPOINT ["python3", "post_app.py"]
