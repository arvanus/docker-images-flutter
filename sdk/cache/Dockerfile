FROM arvanus/cirrusci-flutter:latest

RUN mkdir /gencache 
RUN flutter create /gencache
RUN cd /gencache && flutter build apk
RUN rm -rf /gencache/*
RUN flutter create /gencache
RUN cd /gencache && flutter build apk
RUN rm -rf /gencache

#https://cirrus-ci.org/examples/#gradle
RUN rm -rf ~/.gradle/caches/transforms-1
RUN rm -rf ~/.gradle/caches/journal-1
RUN rm -rf ~/.gradle/caches/jars-3/*/buildSrc.jar
RUN find ~/.gradle/caches/ -name "*.lock" -type f -delete