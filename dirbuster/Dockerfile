# dirbuster Dockerfile

FROM openjdk:7-alpine

RUN wget -O ~/DirBuster-1.0-RC1.tar.bz2 https://netactuate.dl.sourceforge.net/project/dirbuster/DirBuster%20%28jar%20%2B%20lists%29/1.0-RC1/DirBuster-1.0-RC1.tar.bz2

RUN tar xvjf ~/DirBuster-1.0-RC1.tar.bz2 && rm ~/DirBuster-1.0-RC1.tar.bz2

# WORKDIR "~/DirBuster-1.0-RC1"

ENTRYPOINT ["java", "-jar", "/DirBuster-1.0-RC1/DirBuster-1.0-RC1.jar", "-H"]
