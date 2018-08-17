//#!/usr/bin/env groovy

pipeline {
  
  environment {
  }
  
  agent any
  
  stages {
    
    stage ('Preparation (Checking out)') {
      echo "Preparation (Checking out)"
    }

    node {
      stage('Building code') {
        echo "Building code"
      }
    }

  stage ('Testing code') {
    parallel CucumberTests: {
        test ('CucumberTests')
    }, JUnitTests: {
      test ('JUnit Tests')
    }, JacocoTests: {
      test ('IntegrationTest')
    }
  }

  //def test(type) { 
  //}

  stage ('Triggering job and fetching artefact after finishing'){
    echo "Triggering job and fetching artefact after finishing"
  }

  stage ('Packaging and Publishing results') {
    echo "Packaging and Publishing results"
  }

  stage ('Asking for manual approval') {
    echo "Asking for manual approval"  
  }

  stage ('Deployment') {
    echo "Deployment"
  }

  stage ('Sending status') {
    echo "Sending status"
  }
  }
}
