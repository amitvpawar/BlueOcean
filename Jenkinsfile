pipeline {
  agent any
  stages {
    stage('Shell') {
      steps {
        sh 'echo "welcome to the pipeline job"'
      }
    }

    stage('Git') {
      steps {
        git(branch: 'main', url: 'https://github.com/amitvpawar/test.git')
      }
    }

    stage('Ansible') {
      steps {
        sshPublisher(publishers: [sshPublisherDesc(configName: 'ansibleserver', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//home/ubuntu/Ansible/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.yml')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
      }
    }

  }
}
