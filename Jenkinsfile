pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
        
        //stage3: publish the artefacts to Nexus

        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VstronixDevOpsLab', classifier: '', file: 'target/VstronixDevOpsLab-0.0.4-snapshot.war', type: 'war']], credentialsId: '16fecffb-7914-4369-be3a-bb20558587cd', groupId: 'com.vstronixdevopslab', nexusUrl: '172.31.10.47:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'VstronixDevOpsLab-SNAPSHOT', version: '0.0.4-snapshot'
            }
        }


        // Stage3 : Deploying
        stage ('Depoly'){
            steps {
                echo ' deploying......'

            }
        }
	}
}