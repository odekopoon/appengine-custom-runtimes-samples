# see https://hub.docker.com/_/clojure/ 
FROM clojure:alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# copy from https://github.com/metosin/compojure-api
# lein do clean, ring uberjar
COPY target/examples.jar /usr/src/app/

#COPY project.clj /usr/src/app/
#RUN lein deps
#
#COPY . /usr/src/app
#RUN lein ring uberjar && mv target/examples.jar .

# Google App Engine expects the runtime to respond to HTTP requests at port 8080.
ENV PORT 8080

CMD ["java", "-jar", "examples.jar"]

# If you handle heath check and so,
# see https://github.com/GoogleCloudPlatform/appengine-custom-runtimes-samples/blob/master/nginx/Dockerfile

