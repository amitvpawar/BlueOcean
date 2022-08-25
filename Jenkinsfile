pipeline{
    agent any
    
    stages{
        stage{
            steps('welcome'){
                sh 'echo  "welcome to project"'
            }
        }
        stage{
            steps('SCM'){
                git branch: 'main', url: 'https://github.com/amitvpawar/test.git'
            }
        }
        stage{
            steps('SCM'){
                git branch: 'main', url: 'https://github.com/amitvpawar/test.git'
            }
        }
        stage{
            steps('Ansible'){
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ansibleserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home/ubuntu/docker/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage{
            steps('Ansible Playbook'){
               sshPublisher(publishers: [sshPublisherDesc(configName: 'ansibleserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'ansible-playbook docker.yml', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
