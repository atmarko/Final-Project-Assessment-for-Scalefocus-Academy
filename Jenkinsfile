pipeline {
  agent any
  environment {
    // Set the KUBECONFIG environment variable
    KUBECONFIG = 'C:/Users/Marko.Mihajlov/.kube/config'
  }
  stages {
    stage('Verify') {
      steps {
        // This command verifies that the authentication and configuration are working correctly
        bat 'kubectl get services'
      }
    }
    stage('Deploy : final-project-wp-scalefocus.') {
      steps {
        script {
        
            // Check if the namespace exists
            def namespace = bat(returnStdout: true, script: 'kubectl get namespace wp --no-headers --ignore-not-found').trim()
                    if (namespace == '') {
                        bat 'kubectl create namespace wp'
                    }
            
            // Deploy the application using Helm
            bat 'helm dependency build C:/Users/Marko.Mihajlov/Desktop/Final-Project-Assessment-for-Scalefocus-Academy-main/Final-Project-Assessment-for-Scalefocus-Academy-main/bitnami/wordpress'
            bat 'helm install final-project-wp-scalefocus C:/Users/Marko.Mihajlov/Desktop/Final-Project-Assessment-for-Scalefocus-Academy-main/Final-Project-Assessment-for-Scalefocus-Academy-main/bitnami/wordpress -f C:/Users/Marko.Mihajlov/Desktop/Final-Project-Assessment-for-Scalefocus-Academy-main/Final-Project-Assessment-for-Scalefocus-Academy-main/bitnami/wordpress/values.yaml --namespace wp'
          }
            
            
        
    
      }
    }
  }
}