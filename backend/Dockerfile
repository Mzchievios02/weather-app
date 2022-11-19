FROM python:3.9-buster

ENV PYTHONUNBUFFERED 1

WORKDIR /my_app

COPY requirements.txt ./

# RUN apt update && apt install libpq-dev python-dev gcc -y
RUN pip install -r requirements.txt

COPY . /my_app

# Install requirements.txt in app dir
RUN cd app
COPY requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt
RUN pip install gunicorn

CMD ["python3","app/main.py"]

# Use this to debug file structure
# FROM busybox
# COPY . /build-context
# WORKDIR /build-context
# CMD find .
# CMD ["pwd"]