pipeline {
  agent any
  
  tools{
        jdk 'jdk17'
        maven 'maven3'
        }
  environment {
        SCANNER_HOME = tool 'sonar-scanner'
    }
    
  stages {
    stage('Git Checkout') {
      steps {
        // Git checkout
           git branch: 'main', url: 'https://github.com/nishantg98/Boardgame.git'
        }
    }
    
    stage('Maven Compile') {
        steps {
          sh 'mvn compile'
        }
    }
    stage('Test') {
            steps {
              sh 'mvn test'
            }
        }
        
    stage('File System Scan'){
            steps{
                sh "trivy fs --format table -o trivy-fs-report.html ."
            }
        } 
        
    stage('SonarQube Analysis') {
            steps {
              withSonarQubeEnv('sonar') {
                 sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Boardgame \
                 -Dsonar.java.binaries=. \
                 -Dsonar.projectKey=Boardgame '''
               }
            }
        }
        
    stage('Quality Gate') {
      steps {
         script {
             waitForQualityGate abortPipeline: false, credentialsId: 'sonartoken'
            }
        }
    }
    
    stage('Maven Package') {
      steps {
        // Maven package
          sh 'mvn package'
        }
    }
    
    stage('Nexus Build') {
      steps {
         withMaven(globalMavenSettingsConfig: '4ce31901-0a0e-4dcc-a149-47aa1d6d492f', jdk: 'jdk17', maven: 'maven3', mavenSettingsConfig: '', traceability: true) {
          sh "mvn deploy"
    }

        }
    }
    stage('Build Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockercred', toolName: 'docker') {
                        sh "docker build -t nishantg98/boardgame:latest ."
                    }
                }
            }
        }
        
        stage('Trivy Scan'){
            steps{
                sh "trivy image --format table -o trivy-image-report.html nishantg98/boardgame:latest "
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'dockercred', toolName: 'docker') {
                        sh "docker push nishantg98/boardgame:latest"
                    }
                }
            }
        }
        stage('Deploy to EKS') {
           steps {
             withKubeConfig(caCertificate: '', clusterName: 'my-eks-devops', contextName: '',
             credentialsId: 'kubecred', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://744068A09E84BFBF491C76C76E6A6A5C.gr7.us-east-1.eks.amazonaws.com') {
                   sh "kubectl apply -f deployment-service.yaml -n webapps"
                         sleep 60
                }
            }
        }
        stage('Verify deployment') {
            steps {
               withKubeConfig(caCertificate: '', clusterName: 'my-eks22', contextName: '',
               credentialsId: 'kubecred', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://744068A09E84BFBF491C76C76E6A6A5C.gr7.us-east-1.eks.amazonaws.com') {
                     sh "kubectl get pods -n webapps"
                     sh "kubectl get svc -n webapps"
                }
            }
        }
    }
    post {
    always {
        script {
            def jobName = env.JOB_NAME
            def buildNumber = env.BUILD_NUMBER
            def pipelineStatus = currentBuild.result ?: 'UNKNOWN'
            def bannerColor = pipelineStatus.toUpperCase() == 'SUCCESS' ? 'green' : 'red'
            def body = """
                <html>
                <body>
                <div style="border: 4px solid ${bannerColor}; padding: 10px;">
                <h2>${jobName} - Build ${buildNumber}</h2>
                <div style="background-color: ${bannerColor}; padding: 10px;">
                <h3 style="color: white;">Pipeline Status: ${pipelineStatus.toUpperCase()}</h3>
                </div>
                <p>Check the <a href="${BUILD_URL}">console output</a>.</p>
                </div>
                </body>
                </html>
                  """
                emailext (
                     subject: "${jobName} - Build ${buildNumber} - ${pipelineStatus.toUpperCase()}",
                     body: body,
                     to: 'nishantg2798@gmail.com',
                     from: 'jenkins@example.com',
                     replyTo: 'jenkins@example.com',
                     mimeType: 'text/html',
                     attachmentsPattern: 'trivy-image-report.html'
                )
            }
        }
    }
} 
