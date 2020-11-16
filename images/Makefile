all:
	docker build . -t echomantra

test:
	wget -nc https://github.com/alphacep/vosk-api/archive/0.3.15.tar.gz
	tar -xvf 0.3.15.tar.gz
	mv vosk-api-0.3.15 vosk/
	docker run -v $(PWD)/vosk/python/example/:/test -e FILE=/test/test.wav echomantra:latest

distclean:
	rm -rf *.tar.gz
	rm -rf vosk/

