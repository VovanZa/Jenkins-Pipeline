pipeline {
        agent any
        
        stages {
                stage ('Preparation (Checking out)') {
                        steps {
                                echo "Preparation (Checking out)"
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
                
                stage ('Triggering job and fetching artefact after finishing') {
                        echo "Triggering job and fetching artefact after finishing"
                }
        }
}
               
      
