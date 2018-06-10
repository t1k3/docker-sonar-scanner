FROM java:8-jre-alpine

ARG SONAR_SCANNER_VERSION
ENV SONAR_SCANNER_VERSION=${SONAR_SCANNER_VERSION:-3.1.0.1141}

ADD "https://sonarsource.bintray.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip" /

RUN unzip "sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip" \
	&& rm /sonar-scanner-cli-${SONAR_SCANNER_VERSION}.zip \
	&& mkdir -p /var/www/html

ENV PATH "/sonar-scanner-${SONAR_SCANNER_VERSION}/bin:${PATH}"

WORKDIR /var/www/html
CMD sonar-scanner -Dsonar.projectBaseDir=/var/www/html
