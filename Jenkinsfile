pipeline {
        agent any
        
        stages {
                stage ('Preparation (Checking out)') {
                        steps {
                                checkout scm
                                echo "Preparation (Checking out)"
                        }
                }

                stage ('Building code') {
                        steps {
                                echo "Building code"
                        }
                }
                
                stage ('Testing code') {
                        steps {
                                parallel (
                                "CucumberTests": {
                                        echo "CucumberTests"
                                },
                                "JUnitTests": {
                                        echo "JUnitTests"
                                },       
                                "JacocoTests": {
                                        echo "IntegrationTest"
                                }
                                )
                        }                     
                }       
                
                stage ('Triggering job and fetching artefact after finishing') {
                        steps {
                                echo "Triggering job and fetching artefact after finishing"
                        }
                }

                stage ('Asking for manual approval') {
                        steps {
                                echo "Asking for manual approval"  
                        }
                }
                
                stage ('Deployment') {
                        steps {
                                echo "Deployment"
                        }
                }

                stage ('Sending status') {
                        steps {
                                echo "Sending status"
                        }
                }
        }
        
  }                  
      
