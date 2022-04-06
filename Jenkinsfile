pipeline {
agent any
 tools { 
 maven 'maven3.8.4'
 }

 stages {
   stage('building slave1') {
   steps {
build job: 'new-pipe', parameters: [[$class: 'NodeParameterValue', name: 'slave01', labels: ['label1'], nodeEligibility: [$class: 'AllNodeEligibility']]]
        }
    }
}
