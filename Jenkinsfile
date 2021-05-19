pipeline{
    agent any

    stages {
        stage('Compilar') {
            steps {
                echo 'Compilando el codigo de SpringBoot'
		sh './mvnw compile'
            }
        }
	stage('test') {
	    steps {
		echo "Estoy probando el codigo de Sprint Boot"
		sh './mvnw test'
	    }
	}
	stage('Generar JAR') {
	    steps {
		echo "Estoy generando el JAR de Sprint Boot"
		sh './mvnw package'
	    }
	}
	stage('package') {
	    steps {
		echo "Estoy probando el codigo de Sprint Boot"
		sh './mvnw package'
	    }
	}
    }
}

