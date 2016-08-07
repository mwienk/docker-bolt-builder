Docker builder for Bolt CMS
===========================

Use this file to build your Bolt CMS with Docker.
You can use it in Gitlab CI to run the unit tests.

For example:

```
build:dependencies:
  stage: build
  image: mwienk/docker-bolt-builder
  script:
   - composer install
  artifacts:
    paths:
     - ./vendor

test:phpunit:
  stage: test
  image: mwienk/docker-bolt-builder
  script:
   - ./vendor/bin/phpunit
```
