podTemplate(containers:[
    containerTemplate(name: 'jnlp', 
	image: 'jenkins/jnlp-slave', 
	ttyEnabled: true, 
	command: 'cat')
  ]) {
    node() {
    stage('Deploy app add2vals'){
	  container('jnlp'){
        sh 'echo hello world'
	  }
    }
	}
	}

