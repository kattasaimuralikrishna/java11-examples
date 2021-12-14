node('mvn_3.8.4') {
    stage('git') {
        git 'https://github.com/kattasaimuralikrishna/java11-examples.git'
    }
    stage('build'){
        sh '/usr/local/apache-maven-3.8.4/bin/mvn clean package'
        sh ''''
          echo PATH=${PATH}
            echo M2_HOME=${M2_HOME}
      ''''
    }
    stage('archive artifacts') {
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage('publish test reports'){
        junit '**TEST/*.xml'
    }
}