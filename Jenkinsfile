def label = "add2vals"
podTemplate(label: label, containers:[
    containerTemplate(name: 'add2vals', 
	image: 'python:2-alpine', 
	ttyEnabled: true, 
	command: 'cat')
  ]) {
    node(label) {
    stage('Deploy app add2vals'){
	  git 'https://github.com/weinick/simple-python-pyinstaller-app.git'
	  container('add2vals'){
        stage('Build') { 
            steps {
			    cd simple-python-pyinstaller-app
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
                stash(name: 'compiled-results', includes: 'sources/*.py*') 
            }
        }
	  }
    }
	}
	}
