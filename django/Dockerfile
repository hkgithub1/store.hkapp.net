FROM python:3.8-alpine
ENV PYTHONUNBUFFERED 1
WORKDIR /django
RUN apk add build-base
COPY /ComicsDocker/django/requirements.txt .
RUN pip3 install -r requirements.txt
COPY /ComicsDocker/django .

EXPOSE 8000

RUN chmod +x /django/docker-entrypoint.sh

ENTRYPOINT ["/django/docker-entrypoint.sh"]
