FROM python:3

ENV PYTHONUNBUFFERED 0

RUN apt-get update && apt-get -y install libpq-dev python-dev
RUN apt-get -y install binutils libproj-dev gdal-bin

WORKDIR /app

ADD manage.py /app/
ADD requirements.txt /app/
RUN pip install -r requirements.txt

ADD compose/start.sh /start.sh
RUN chmod +x /*.sh