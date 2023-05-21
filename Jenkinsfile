pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clonar el repositorio de GitHub que contiene el proyecto JMeter
                git 'https://github.com/daniel-garciaQACG/Jmeter.git'
            }
        }

        stage('Run JMeter') {
            steps {
                // Ejecutar el script JMeter
                bat "\"${tool 'JMeter'}/bin/jmeter\" -n -t Script.jmx -l report.jtl"
            }
        }

        stage('Publish Report') {
            steps {
                // Publicar el informe de JMeter en Jenkins
                junit 'report.jtl'
            }
        }
    }
}
