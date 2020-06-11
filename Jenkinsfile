node {

    stage('Clone Repository') {
        checkout scm
                }

    stage('Configure Compliance CI Rule in Console') {
        withCredentials([usernamePassword(credentialsId: 'twistlock_creds', passwordVariable: 'TL_PASS', usernameVariable: 'TL_USER')]) {
            sh 'curl -i -k -s -u $TL_USER:$TL_PASS -H "Content-Type: application/json" -X PUT -d "@compliance-ci-rule.json" https://$TL_CONSOLE/api/v1/policies/compliance/ci/images'
        }
    }
}
