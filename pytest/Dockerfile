FROM python:3.6-stretch

WORKDIR /app
RUN pip install --upgrade pip && pip install pipenv
RUN pipenv install pytest tox

