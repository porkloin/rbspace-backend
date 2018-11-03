# RBSpace-backend

[![CircleCI](https://circleci.com/gh/porkloin/rbspace-backend.svg?style=shield)](https://circleci.com/gh/porkloin/rbspace-backend)
[![Dashboard rbspace-backend](https://img.shields.io/badge/dashboard-rbspace_backend-yellow.svg)](https://dashboard.pantheon.io/sites/599d51e8-07e0-4a90-b7ed-f88f1f66b635#dev/code)
[![Dev Site rbspace-backend](https://img.shields.io/badge/site-rbspace_backend-blue.svg)](http://dev-rbspace-backend.pantheonsite.io/)
[![Gatsby Front-End Site rbspace-frontend](https://img.shields.io/badge/site-rbspace_frontend-red.svg)](http://www.ryanbateman.space/)
[![Front-End Repo](https://img.shields.io/badge/site-Front_End_Repo-orange.svg)](http://www.github.com/porkloin/rbspace-frontend)

## Ryan Bateman Dot Space - "Backend" Edition :neckbeard:

This repo is a Drupal 8 codebase that runs the backend website for my Blog, [Ryan Bateman Dot Space](http://www.ryanbateman.space).

### Decoupled Architecture

This codebase is designed to serve exclusively as a content repository for a completely separate front-end website. It serves site contents via [Drupal 8's JSONAPI Module](https://www.drupal.org/project/jsonapi) and serves them via a statically-built [GatsbyJS](http://gatsbyjs.org/) website.

### Workflow

The Drupal 8 codebase is managed via [Composer](http://getcomposer.org) for dependency management and resolution, uses [CircleCI](http://circleci.com/) as a build CI/CD server, and deploys build artifacts to [Pantheon](https://pantheon.io/).

### Developing

This repo includes configurations for local development on [DDEV](http://ddev.readthedocs.io/). Once you've installed DDEV, run `ddev start` from the repo root to stand up a local dev server.

### Pull Requests

Opening a pull request will trigger a Circle CI build and test. Assuming our PHPUnit tests pass, Circle will automatically create a Pantheon Multi-Dev environment for us to test our work in.

When pull requests are closed (merged into Master), Circle will build, test, and deploy the artifact to our DEV environment on Pantheon.

### Triggering Front-End Builds

Using the [Webhooks module](https://www.drupal.org/project/webhooks), we can trigger front-end rebuilds on any node save, update, or delete operation. The front end can be seen [here](http://www.ryanbateman.space).