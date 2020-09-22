pipeline {
    agent none 
	podTemplate(containers: [
    containerTemplate(name: 'add2vals', image: 'python:2-alpine', ttyEnabled: true, command: 'cat')
  ]) {
    node(POD_LABEL) {
    stages('Deploy app add2vals'){
	  container('add2vals'){
        stage('Build') { 
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
	  }
    }
	}
	}
}