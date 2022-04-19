FROM python:latest

COPY /requirements.txt .
COPY /.env .
RUN pip install -r requirements.txt
RUN mkdir video
COPY / .

CMD python manage.py makemigrations
CMD python manage.py runserver