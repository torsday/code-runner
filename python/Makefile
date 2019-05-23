build:
	# remove all cached pyc files
	find . -name "*.pyc" -delete
	docker image build -t code-runner-py .
run:
	docker container run \
		-v "${CURDIR}/src":/src \
		code-runner-py
sh:
	# get a shell in docker
	docker container run \
		-v "${CURDIR}/src":/src \
		-it code-runner-py /bin/sh

shd:
	# run shell in detached mode
	docker container run -d \
		-v "${CURDIR}/src":/src \
		-it code-runner-py /bin/sh

lintfix:
	autopep8 --in-place --aggressive --aggressive --max-line-length 120 -r src
