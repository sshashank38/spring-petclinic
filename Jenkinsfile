
node('SPC') {

    stage('scm') {
        git branch: 'main', credentialsId: 'jenkins_key1', url: 'https://github.com/sshashank38/spring-petclinic.git'
    }

    stage('build') {
        sh 'mvn clean package'
    }

    stage('postbuild'){
        junit '**/TEST-*.xml'
        archiveArtifacts artifacts: '**/*.war', followSymlinks: false
    }
}