pipeline {
    agent any
    
    stages {
        stage('welcome') {
            steps {
                sh 'echo  "welcome to project"'
            }
        }
        stage('SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/amitvpawar/test.git'
            }
        }
        stage('Ansible') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansibleserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home/ubuntu/docker/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage('Ansible Playbook') {
            steps {
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ansibleserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook docker.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
