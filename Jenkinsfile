pipeline {
    agent any

    stages {
        stage('Deploy  to kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://A4986961750F82F7C53092E8A3279016.gr7.eu-central-1.eks.amazonaws.com']]) {
                sh "kubectl apply -f deployment-service.yml"
                
}
            }
        }
        stage('verify  deployment') {
            steps {
               withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://A4986961750F82F7C53092E8A3279016.gr7.eu-central-1.eks.amazonaws.com']]) {
                sh "kubectl get svc -n webapps"
            
            }
        }
    }
}
}
