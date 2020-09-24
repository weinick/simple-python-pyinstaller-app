def label = "add2vals"
podTemplate(label: label, containers:[
    containerTemplate(name: 'add2vals', 
	image: 'maven:3.3.9-jdk-8-alpine', 
	ttyEnabled: true, 
	command: 'cat')
  ]) {
    node(label) {
    stage('Deploy app add2vals'){
	  git 'https://github.com/jenkinsci/kubernetes-plugin.git'
	  container('add2vals'){
        stage('Build') { 
            sh 'mvn -DskipTests -B clean install'

        }
	  }
    }
	}
	}
