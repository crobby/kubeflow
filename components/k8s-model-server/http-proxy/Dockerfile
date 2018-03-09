FROM centos/python-27-centos7

ENV LD_LIBRARY_PATH=/opt/rh/python27/root/usr/lib64
EXPOSE 8888

USER root

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY . /usr/src/app

RUN pip install --upgrade pip
RUN pip install -r requirements/production.txt

ENTRYPOINT ["python", "/usr/src/app/server.py"]
