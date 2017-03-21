# see https://hub.docker.com/_/clojure/ 
FROM clojure:alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# copy from "lein new compojure hello-world"
COPY project.clj /usr/src/app/
RUN lein deps

COPY . /usr/src/app
RUN mv "$(lein ring uberjar | sed -n 's/^Created \(.*standalone\.jar\)/\1/p')" app-standalone.jar

# Google App Engine expects the runtime to respond to HTTP requests at port 8080.
ENV PORT 8080

CMD ["java", "-jar", "app-standalone.jar"]

# If you handle heath check and so,
# see https://github.com/GoogleCloudPlatform/appengine-custom-runtimes-samples/blob/master/nginx/Dockerfile

