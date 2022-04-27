pipeline{
    agent{
        label "master"
    }
    stages{
        stage('Checkout Source'){
            steps {
                git url: "https://github.com/sheikzaidh/jenkins-sample.git", branch: "master"
            }
        }

        stage("Deploy App"){
            steps {
                script {
                    kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
                }
            }
        }
    }
}