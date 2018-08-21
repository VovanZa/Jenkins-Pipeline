pipeline {
        agent any
        
        tools {
                gradle "gradle4.9"
        }
        stages {
                stage ('Preparation (Checking out)') {
                        steps {
                                checkout scm
                                echo "Preparation (Checking out)"
                        }
                }

                stage ('Building code') {
                         steps {
                                build job: 'Create4Jobs'
                                echo "Building code"
                        }
                }
                
                stage ('Testing code') {
                        steps {
                                parallel (
                                        "CucumberTests": {
                                                sh 'gradle --version'
                                                sh 'gradlew clean'
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
//                        input {
//                                message "Deploy artefact?"
//                                ok "Yes, deploy"
//                        }        
                        steps {
                                echo "Asking for manual approval"  
//                                echo "Yes, deploy artefact"
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
      
