FROM alpine:3

ENV MAVEN_VERSION=3.6.3
ENV USER_HOME_DIR="/root"
ENV BASE_URL=https://apache.osuosl.org/maven/maven-3/${MAVEN_VERSION}/binaries
ENV JAVA_HOME /usr/lib/jvm/default-jvm/
ENV MAVEN_HOME /usr/share/maven
ENV MAVEN_CONFIG "$USER_HOME_DIR/.m2"

# Install OpenJDK & packages
RUN apk --update --no-cache add openjdk16

# Install alpine pacakges
RUN apk --update --no-cache add \
    curl \
    wget \
    ca-certificates

# Install Python3 & pip3
RUN apk add --update --no-cache python3 py3-pip && ln -sf python3 /usr/bin/python

# Install Maven 3.6
RUN mkdir -p /usr/share/maven /usr/share/maven/ref \
 && curl -fsSL -o /tmp/apache-maven.tar.gz ${BASE_URL}/apache-maven-${MAVEN_VERSION}-bin.tar.gz \
 && tar -xzf /tmp/apache-maven.tar.gz -C /usr/share/maven --strip-components=1 \
 && rm -f /tmp/apache-maven.tar.gz \
 && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

# Define working directory
WORKDIR /data

# Define default command
CMD ["mvn", "--version"]