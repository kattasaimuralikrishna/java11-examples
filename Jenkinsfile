node('mvn_3.8.4') {
    stage('git') {
        git 'https://github.com/kattasaimuralikrishna/java11-examples.git'
    }
    stage('build'){
        sh 'mvn clean package'
    }
    stage('archive artifacts') {
        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }
    stage('publish test reports'){
        junit '**TEST/*.xml'
    }
}