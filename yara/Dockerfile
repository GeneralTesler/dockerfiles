FROM ubuntu:latest
LABEL maintainer "2xxe <@2xxeformyshirt>"

RUN apt-get update && apt-get install -y \
			automake \
			libtool \
			make \
			gcc \
			git \
			wget \
			libssl-dev \
			libjansson-dev \
			libmagic-dev \
			&& mkdir /opt/yara \
			&& cd /opt/yara \
			&& wget https://github.com/VirusTotal/yara/archive/v3.7.1.tar.gz \
			&& tar -zxf v3.7.1.tar.gz \
			&& rm v3.7.1.tar.gz \
			&& cd yara-3.7.1 \
			&& ./bootstrap.sh \
			&& ./configure --with-crypto --enable-cuckoo --enable-magic --enable-dotnet \
			&& make \
			&& make install \
			&& cd .. \
			&& git clone https://github.com/Yara-Rules/rules.git
WORKDIR /opt/yara
