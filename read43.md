# Building Docker Images with heroku.yml
The heroku.yml file is a manifest you can use to define your Heroku app. It allows you to:

- Build Docker images on Heroku
- Specify add-ons and config vars to create during app provisioning
- Take advantage of Review Apps when deploying Docker-based applications
## Getting started
1. Create a `heroku.yml` file in your application’s root directory. The following example `heroku.yml` specifies the Docker image to build for the app’s web process:
```
build:
  docker:
    web: Dockerfile
run:
  web: bundle exec puma -C config/puma.rb
```
In this example, both heroku.yml and Dockerfile are in the same directory. If the Dockerfile lives in a non-root directory, specify the relative path in the build.docker.web value, such as app/Dockerfile.

If you don’t include a run section, Heroku uses the CMD specified in the Dockerfile
2. Commit the file to your repo:
```
git add heroku.yml
git commit -m "Add heroku.yml"
```
3. Set the stack of your app to container:
```
heroku stack:set container
```
4. Push your app to Heroku
```
git push heroku master
```
Your application will be built, and Heroku will use the run command provided in heroku.yml instead of your Procfile.
## heroku.yml Overview

A `heroku.yml` manifest has 4 top-level sections:

`setup` - Specifies the add-ons and config vars to create during app provisioning
`build` - Specifies the Dockerfile to build
`release` - Specifies the release phase tasks to execute
`run` - Specifies process types and the commands to run for each
Details for each of these sections are described below.

Here’s an example that illustrates using a` heroku.yml` manifest to build Docker images:
```
setup:
  addons:
    - plan: heroku-postgresql
      as: DATABASE
  config:
    S3_BUCKET: my-example-bucket
build:
  docker:
    web: Dockerfile
    worker: worker/Dockerfile
  config:
    RAILS_ENV: development
    FOO: bar
release:
  command:
    - ./deployment-tasks.sh
  image: worker
run:
  web: bundle exec puma -C config/puma.rb
  worker: python myworker.py
  asset-syncer:
    command:
      - python asset-syncer.py
    image: worker
```   







