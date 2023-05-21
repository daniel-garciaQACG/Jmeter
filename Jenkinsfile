pipeline {
    agent any

    stages {
        stage('Ejecutar JMeter') {
            steps {
                bat 'C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\jmeter -jjmeter.save.saveservice.output_format=xml -n -t Script.jmx -l C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\report.jtl'
            }
        }
        stage('Publicar resultados de rendimiento') {
            steps {
                perfReport sourceDataFiles: 'C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\report.jtl'
            }
        }
        
         stage('Resultado HTML') {
            steps {
                bat 'del C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\Resultado'
                bat 'rmdir /s /q C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\HTMLREPORT'
                bat 'C:\\Users\\dagam\\Desktop\\apache-jmeter-5.5\\bin\\jmeter -n -t C:\Users\dagam\Desktop\apache-jmeter-5.5\bin\Script.jmx -l Resultado -e -o C:\Users\dagam\Desktop\apache-jmeter-5.5\bin\HTMLREPORT'
            }
        }
    }
}
