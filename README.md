FROM continuumio/miniconda3:latest

WORKDIR /App

RUN apt-get update \
    && apt-get upgrade -y

RUN apt-get install python -y

RUN pip install --upgrade pip

RUN pip install mlflow

RUN pip install boto3

RUN pip install pymysql

COPY ./1.sh /App

RUN chmod u+x /App/1.sh

RUN /App/1.sh
