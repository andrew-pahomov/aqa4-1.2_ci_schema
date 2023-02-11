node {

    stage('Preparation') {
        git 'https://github.com/andrew-pahomov/aqa4-1.2_ci_schema'
    }

    stage('Start SUT') {
        sh 'java -jar artifacts/app-mbank.jar &'
    }

    stage('Test') {
        if (isUnix()) {
            sh 'chmod +x gradlew'
            sh './gradlew clean test -Dselenide.headless=true --info'
        } else {
            bat 'gradlew clean test -Dselenide.headless=true --info'
        }
    }

}