
node('SPC') {

    stage('scm') {
        git credentialsId: 'jenkins_key1', url: 'https://github.com/sshashank38/spring-petclinic'
    }

    stage('build') {
        sh 'mvn clean package'
    }

    stage('postbuild'){
        junit '**/TEST-*.xml'
        archiveArtifacts artifacts: '**/*.war', followSymlinks: false
    }
}