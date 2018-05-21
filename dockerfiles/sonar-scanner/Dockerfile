FROM java:8-jre-alpine

ARG SONAR_SCANNER_WORKDIR=/var/www/html

ARG SONAR_SCANNER_VERSION
ENV SONAR_SCANNER_VERSION=${SONAR_SCANNER_VERSION:-3.1.0.1141}

ADD "https://sonarsource.bintray.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip" /

RUN unzip "sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip" \
	&& rm /sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip \
	&& mkdir -p ${SONAR_SCANNER_WORKDIR}

ENV PATH "/sonar-scanner-${SONAR_SCANNER_VERSION}/bin:${PATH}"

CMD sonar-scanner -Dsonar.projectBaseDir=${SONAR_SCANNER_WORKDIR}
