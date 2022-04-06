pipeline {
agent any
 tools { 
 maven 'maven3.8.4'
 }

 stages {
   stage('building slave1') {
   steps {
build job: 'new-pipe', parameters: [[$class: 'LabelParameterValue', name: 'slave01', label: 'label1']]
}
}

   stage ('building slave2') {
   steps {
   build job: 'nexus', parameters: [[$class: 'LabelParameterValue', name: 'slave2', label: 'label2']]
   }
}
}
}
