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
    }
}

