pipeline {
 parameters {
  choice(choices: ['Dev', 'QA'], description: 'Target for build env', name: 'env')
  choice(choices: ['Y','N'], description: 'is the deployment for release' , name: 'isRelease')

}
agent any
 tools { 
 maven 'maven3.8.4'
 }

 stages {
   stage('building') {
   steps {
    script {
     if ("${params.env}" == 'Dev') {
              build job: 'new-pipe', parameters: [[$class: 'NodeParameterValue', name: 'slave01', labels: ['label1'], nodeEligibility: [$class: 'AllNodeEligibility']]]
    }
    else{
                build job: 'nexus', parameters: [[$class: 'NodeParameterValue', name: 'slave02', labels: ['label2'], nodeEligibility: [$class: 'AllNodeEligibility']]]
        }
    }
       }
       }
 } 
}

