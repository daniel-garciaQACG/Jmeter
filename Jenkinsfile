pipeline {
    agent any

    stages {
        stage('Ejecutar JMeter') {
            steps {
                bat 'C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\jmeter -jjmeter.save.saveservice.output_format=xml -n -t Script.jmx -l C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Pruebas-Jmeter\\report.jtl'
            }
        }
        stage('Publicar resultados de rendimiento') {
            steps {
                perfReport sourceDataFiles: 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Pruebas-Jmeter\\report.jtl'
            }
        }
        
         stage('Resultado HTML') {
            steps {
                bat 'del Resultado'
                bat 'rmdir /s /q Reporte'
                bat 'mkdir Reporte'
                bat 'C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\jmeter -n -t Script.jmx -l Resultado -e -o C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Pruebas-Jmeter\\Reporte'
            }
        }
    }
}
