FROM python:3.8-slim

RUN mkdir /var/www

WORKDIR /var/www/

COPY ["requirements.txt", "./"] 

RUN python3 -m pip install -r requirements.txt

EXPOSE 8080

COPY ["app.py", "./"]

ENTRYPOINT ["gunicorn"]

CMD ["app:app", "--bind=0.0.0.0:8000", "--workers=4", "--log-level=debug", "--reload"]