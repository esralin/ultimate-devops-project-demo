FROM python:3.12-slim-bookworm AS base

WORKDIR /usr/src/app

COPY requirements.txt ./

RUN python -m pip install --upgrade pip
RUN python -m pip install setuptools==69.5.1
RUN pip install -r requirements.txt

COPY . .


RUN python -c "import pkg_resources; print('pkg_resources works')"
RUN opentelemetry-bootstrap -a install 

ENV RECOMMENDATION_PORT=1010

ENTRYPOINT ["python", "recommendation_server.py"]
