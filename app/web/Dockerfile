FROM python:latest

COPY /requirements.txt .
COPY /.env .
RUN pip install -r requirements.txt
RUN mkdir video
COPY / .
EXPOSE 8000

##########################################
# Dockerfile to change from root to 
# non-root privilege
###########################################
# Add a new user "user" with user id 8877
RUN useradd -u 8877 user

# Change to non-root privilege
USER user
#RUN python /manage.py makemigrations
#RUN python /manage.py runserver

##########################################
# Add HEALTHCHECK instruction to the container image
# Based on the reported health status, the docker engine could then exit non-working containers and instantiate new ones
###########################################
HEALTHCHECK --interval=5m --timeout=3s \
  CMD curl -f http://localhost/ || exit 1