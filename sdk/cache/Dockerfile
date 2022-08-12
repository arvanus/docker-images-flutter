FROM arvanus/cirrusci-flutter:latest

RUN mkdir /gencache
RUN cd /gencache/
RUN flutter create .
RUN flutter build apk
RUN rm -rf /gencache/*
RUN flutter create .
RUN flutter build apk

RUN rm -rf /gencache
RUN rm -rf ~/.gradle/caches/transforms-1
RUN rm -rf ~/.gradle/caches/journal-1
RUN rm -rf ~/.gradle/caches/jars-3/*/buildSrc.jar
RUN find ~/.gradle/caches/ -name "*.lock" -type f -delete