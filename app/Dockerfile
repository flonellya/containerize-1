# your code goes here ...
FROM python:3.6.7

#change to the app user
RUN mkdir -p /home/app/server
RUN apt update && apt install -y vim
WORKDIR /home/app/server
COPY src/requirements.txt /home/app/server
RUN pip install --upgrade pip --user
RUN  python -m pip install -r requirements.txt
COPY src /home/app/server

