FROM ubuntu:18.04
MAINTAINER yz667@duke.edu

RUN apt-get update -y
RUN apt-get install python3-pip -y
RUN apt-get install gunicorn3 -y

COPY requirements.txt  requirements.txt
COPY flask-app /opt/

RUN pip3 install -r requirements.txt
WORKDIR /opt/

CMD ["gunicorn3", "-b", "0.0.0.0:8000", "flask-app:app", "--workers=5"]