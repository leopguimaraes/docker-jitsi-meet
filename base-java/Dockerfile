ARG JITSI_REPO=jitsi
FROM ${JITSI_REPO}/base

ADD https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public /tmp/openjdk.key

RUN	\
	mkdir -p /usr/share/man/man1 && \
	apt-key add /tmp/openjdk.key && \
	rm -f /tmp/openjdk.key && \
	echo "deb https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/ buster main" > /etc/apt/sources.list.d/openjdk.list && \
	apt-dpkg-wrap apt-get update && \
	apt-dpkg-wrap apt-get install -y adoptopenjdk-8-hotspot-jre && \
	apt-cleanup
