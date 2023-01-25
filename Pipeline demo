pipeline {
   agent any 
        stages {
           stage ('one') { 
               steps { echo 'Hi, This is venkatesh' } 
           }
           stage ('two') {
              steps { input ('Do you want to proceed' ) }
              }
            stage ('Three') {
              when {
                  not { 
                       branch "master"
                       }
                      }
                      steps { echo "hello" }
                      }
             stage ('Four') {
               parallel { 
                  stage ('Unit Test' ) {
                         steps { 
                            echo 'Running the unit test...' 
                            }
                         }
                   stage ( 'Integration Test' ) {
                                 agent { 
                                     docket {
                                         reuseNode false
                                         image 'ubuntu'
                                         }
                                        }
                                       }
                                      steps { 
                                      echo 'Running the integration test...' 
                                      }
                                     }
                                   }
