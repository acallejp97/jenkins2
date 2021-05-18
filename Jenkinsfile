pipeline{
    agent any

    stages {
        stage('Compilar') {
            steps {
                echo 'Compilando el codigo de SpringBoot'
		sh './mvnw compile'
            }
        }
    }
}

