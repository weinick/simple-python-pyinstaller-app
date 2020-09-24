podTemplate(containers:[
    containerTemplate(name: 'jnlp', 
	image: 'jenkins/jnlp-slave', 
	ttyEnabled: true, 
	command: 'cat')
  ]) {
    node() {
    stage('Deploy app add2vals'){
	  git 'https://github.com/weinick/simple-python-pyinstaller-app.git'
	  container('jnlp'){
        sh 'echo hello world'
	  }
    }
	}
	}

