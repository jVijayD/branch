pipeline {
agent any
 tools { 
 maven 'maven3.8.4'
 }
 
node('slave01') {
    build 'new-pipe'
}
node('slave2') {
    build 'mutli-pipeline'
}

 stages {
   stage('building slave1') {
   steps {
build job: 'new-pipe', parameters: [[$class: 'LabelParameterValue', name: 'slave01', label: 'jenkins']]
}
}

   stage ('building slave2') {
   steps {
   build job: 'multi-pipeline', parameters: [[$class: 'LabelParameterValue', name: 'slave2', label: 'jenkins']]
   }
}
}
}
