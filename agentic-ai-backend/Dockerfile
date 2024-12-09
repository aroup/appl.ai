FROM python:3.10-slim

WORKDIR /app

COPY ./config/requirements.txt /app/

RUN apt-get update && apt-get install -y git poppler-utils

RUN pip install -r requirements.txt

COPY ./app.py /app/

ENV FLASK_APP=app.py

EXPOSE 80

CMD ["flask", "run", "--host=0.0.0.0", "--port=80", "--debug"]