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
            post {
		failure {
		    sh "rm -rf ./target"
	    }
	}
	stage('package') {
	    steps {
		echo "Estoy probando el codigo de Sprint Boot"
		sh './mvnw package'
	    }
	}
    }
    post {
        success {
	    echo "Todo ha funcionado correctamente" 
	}
    }
}

