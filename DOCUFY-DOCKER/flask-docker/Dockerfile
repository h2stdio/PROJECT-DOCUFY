FROM python:3.7


COPY Docufy/requirements.txt requirements.txt
COPY Docufy /opt/

RUN apt-get update
RUN apt-get install -y gcc g++ gfortran libopenblas-dev liblapack-dev pkg-config
# RUN apt install -y build-essential 

RUN pip3 install -r requirements.txt
WORKDIR /opt/

CMD ["gunicorn3", "-b", "0.0.0.0:8000", "app:app", "--workers=5"]
