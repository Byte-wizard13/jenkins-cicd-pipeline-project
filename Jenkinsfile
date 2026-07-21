pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Cloning code from GitHub...'
                checkout scm
            }
        }
        
        stage('Code Validation') {
            steps {
                echo 'Checking code quality and syntax...'
                // प्रॅक्टिससाठी साधी लिनक्स कमांड
                sh 'ls -la' 
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to Web Server...'
                // हा कोड फाईल सर्व्हरच्या डिरेक्टरीमध्ये कॉपी करेल
                sh 'cp index.html /var/www/html/ || true'
                echo 'Deployment Successful! 🚀'
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline completed successfully! Notify team.'
        }
        failure {
            echo 'Pipeline failed. Check Jenkins logs.'
        }
    }
}
