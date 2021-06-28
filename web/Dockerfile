FROM python:3-slim

RUN apt update && apt upgrade && apt install -y git

RUN git clone https://git.sr.ht/~metalune/simplytranslate_engines engines && \
    git clone https://git.sr.ht/~metalune/simplytranslate_web web

WORKDIR /engines
RUN python3 setup.py install && \
    pip install -r requirements.txt
WORKDIR /web
RUN pip install -r requirements.txt && \
    pip install uvicorn

EXPOSE 5000
CMD ["python3", "main.py"]
