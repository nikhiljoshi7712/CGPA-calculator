pipeline {
    agent any
    
    stages {
        stage('Source Code') {
            steps {
                git branch: 'master', url: 'https://github.com/nikhiljoshi7712/CGPA-calculator'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                sh 'export PATH=$PATH:/usr/local/bin && docker build -t cgpa_calculator .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'export PATH=$PATH:/usr/local/bin && docker run -d --name cgpa_calculator_container -p 5505:5505 cgpa_calculator'
            }
        }
    }
}
