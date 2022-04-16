FROM python:3-slim

RUN apt update && apt -y upgrade && apt install -y git automake libtool g++-multilib-i686-linux-gnu zlib1g-dev  build-essential gcc g++ libxml2 libxml2-dev libxslt1.1 libxslt1-dev

RUN git clone "https://codeberg.org/SimpleWeb/SimplyTranslate-Engines" engines && \
    git clone "https://codeberg.org/SimpleWeb/SimplyTranslate-Web" web

WORKDIR /engines
RUN python3 setup.py install && \
    pip install -r requirements.txt
WORKDIR /web
RUN pip install -r requirements.txt

EXPOSE 5000
CMD ["python3", "main.py"]
