#!/usr/bin/env groovy

node {
  stage('Building code') {
  }
}

stage ('Testing code') {
  parallel CucumberTests: {
      test ('CucumberTests')
  }, JUnitTests: {
    test ('JUnit Tests')
  }, Jacoco Tests: {
    test ('IntegrationTest')
  }
 }

stage ('Triggering job and fetching artefact after finishing'){
}

stage ('Packaging and Publishing results') {
}

stage ('Asking for manual approval') {
}

stage ('Deployment') {
}

stage ('Sending status') {
}

