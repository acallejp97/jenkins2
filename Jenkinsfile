pipeline{
    agent any
    environment{
        author="Asier"
    }
    /* Triggers a lanzar
    triggers {
      upstream 'ProbarAgente'
      pollSCM '* * * * *'
    }
    */
    
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
        }
        stage('deploy') {
            steps {
                echo "Estoy desplegando "
                sh 'cp target/calculadora-0.0.1-SNAPSHOT.jar /tmp'
            }
        }
    }
    post {
        success {
            echo "Todo ha funcionado correctamente"
            sh "echo ${author} > /tmp/f1.txt"
        }
    }
}
