FROM python:3.8-alpine
ENV PYTHONUNBUFFERED 1
WORKDIR /django
RUN apk add build-base
COPY requirements.txt .
RUN pip3 install -r requirements.txt
COPY . .

EXPOSE 8000

RUN chmod +x /django/docker-entrypoint.sh

ENTRYPOINT ["/django/docker-entrypoint.sh"]
