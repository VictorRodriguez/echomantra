FROM centos:latest

RUN yum install -y python3 wget git unzip
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
RUN python3 get-pip.py
RUN pip install vosk

RUN git clone https://github.com/alphacep/vosk-api
RUN cd vosk-api/python/example && wget https://alphacephei.com/kaldi/models/vosk-model-small-en-us-0.3.zip
RUN cd vosk-api/python/example && unzip vosk-model-small-en-us-0.3.zip
RUN cd vosk-api/python/example && mv vosk-model-small-en-us-0.3 model

CMD cd vosk-api/python/example && python3 ./test_simple.py test.wav > result.json && cat result.json

