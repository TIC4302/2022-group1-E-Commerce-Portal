FROM python:latest

COPY /requirements.txt .
COPY /.env .
RUN pip install -r requirements.txt
RUN mkdir video
COPY / .
EXPOSE 8000

RUN useradd -d /home/dockle -m -s /bin/bash dockle
USER dockle
#RUN python /manage.py makemigrations
#RUN python /manage.py runserver