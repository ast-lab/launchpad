FROM docker/compose:1.23.2 as compose
FROM maven:3.6-jdk-8

COPY --from=compose /usr/local/bin/docker /usr/local/bin/docker
COPY --from=compose /usr/local/bin/docker-compose /usr/local/bin/docker-compose

WORKDIR /app

RUN mvn dependency:get -DgroupId=org.apache.maven -DartifactId=maven-core -Dversion=2.0.6
RUN mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-dependency-plugin -Dversion=2.8 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-resources-plugin -Dversion=2.6 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-compiler-plugin -Dversion=3.8.0 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-surefire-plugin -Dversion=2.12.4 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-site-plugin -Dversion=3.3 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-jar-plugin -Dversion=2.4 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-clean-plugin -Dversion=2.5
RUN mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-surefire-report-plugin -Dversion=3.0.0-M3 && \
	mvn dependency:get -DgroupId=org.apache.maven.plugins -DartifactId=maven-surefire-plugin -Dversion=3.0.0-M3

