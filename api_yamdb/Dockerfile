FROM python:3.7-slim

LABEL author='cordy' version=1 broken_brains=1

WORKDIR /app

COPY ./api_yamdb/requirements.txt ./

RUN pip3 install -r ./requirements.txt --no-cache-dir

COPY . .

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
