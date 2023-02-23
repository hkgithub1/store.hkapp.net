FROM python:3.8-alpine
ENV PYTHONUNBUFFERED 1
WORKDIR /django
RUN apk add build-base
RUN cp requirements.txt .
RUN pip3 install -r requirements.txt
RUN cp . .

EXPOSE 8000

RUN chmod +x /django/docker-entrypoint.sh

ENTRYPOINT ["/django/docker-entrypoint.sh"]
