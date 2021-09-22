
pipeline {
    agent any
    stages {
        stage('Prep_Environment') {
          steps {
              echo "Setting Development Environment"
              	sh 'whoami'
                sh 'ctm env set sandbox'
                echo "Environment was set to sandbox"
         } 
       }
       stage('Validate_Workflow') {
         steps {
             echo "Validate Workflow Syntax"
               sh 'ctm build forecast_flow.json'
               echo "Worklow Build Complete"
         }
       }
       stage('Deploy_Workflow') {
         steps {
             echo "Applying Deploy Descriptor Transform and Running Workflow"
               sh 'ctm run forecast_floww.json -e sandbox'
               echo "Worklow Run Complete"
         }
       }

       
    }
}
