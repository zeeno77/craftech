FROM python:3.7-alpine

RUN apk update && apk add postgresql-dev gcc python3-dev musl-dev zlib-dev jpeg-dev graphviz-dev libpq
RUN pip install --upgrade pip
RUN pip install gunicorn

WORKDIR /app
COPY ./backend .
COPY ./Docker/backend/wsgi-entrypoint.sh .
RUN pip install -r requirements.txt

ENTRYPOINT ["/app/wsgi-entrypoint.sh"]
