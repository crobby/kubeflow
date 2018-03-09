# Copyright 2018 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     https://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM centos/python-27-centos7

ENV LD_LIBRARY_PATH=/opt/rh/python27/root/usr/lib64
RUN pip install --upgrade pip
RUN pip install --no-cache-dir grpcio tensorflow tensorflow-serving-api

USER root
RUN mkdir -p /opt/label /data

WORKDIR /opt/label

COPY label.py ./
COPY run.sh ./

ARG IMAGES_DIR=images/

ADD $IMAGES_DIR /data/

ENTRYPOINT ["bash", "run.sh"]
CMD []
