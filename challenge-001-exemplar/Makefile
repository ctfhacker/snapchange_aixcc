all: bzImage harness

challenge: challenge-001-exemplar
	cd challenge-001-exemplar && \
	docker build . -t exemplar-cp-linux:base --target=exemplar-cp-linux-base && \
	sed -i 's_/bin/bash_/usr/bin/env bash_g' ./run.sh && \
	./run.sh pull_source && \
	./run.sh build

challenge-001-exemplar:
	git clone https://github.com/aixcc-public/challenge-001-exemplar

bzImage: challenge
	cp challenge-001-exemplar/src/arch/x86/boot/bzImage .

harness: challenge
	cp challenge-001-exemplar/out/linux_test_harness .

clean:
	rm -rf challenge-001-exemplar

