# Clojure Custom Runtime for App Engine

Simple sample of an [clojure](https://clojure.org/) app that runs on [Google App Engine](https://cloud.google.com/appengine) using the [`clojure`](https://hub.docker.com/_/clojure/) offical Docker image.

## Details

+ `app.yaml` - Configuration file for App Engine. This just declares the runtime is custom and to use the Dockerfile to run the application.
+ `Dockerfile` - Defines your docker image. It extends from the official clojure Docker image and adds project.
+ `project.clj` - A basic clojure configuration file.
