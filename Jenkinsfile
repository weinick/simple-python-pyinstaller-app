def label = "master"
podTemplate(containers:[
    containerTemplate(name: 'maven', 
	image: 'maven:3.3.9-jdk-8-alpine', 
	ttyEnabled: true, 
	command: 'cat')
  ]) {
    node(label) {
    stage('Deploy app add2vals'){
	  git 'https://github.com/jenkinsci/kubernetes-plugin.git'
	  container('maven'){
	   stage('Build a Maven project')
        sh 'mvn -DskipTests -B clean install'
	  }
    }
	}
	}

