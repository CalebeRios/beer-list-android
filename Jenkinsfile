pipeline {
    agent any
    stages {
        stage('Pre-Build') {
            steps {
                sh 'export ANDROID_SERIAL=$(adb devices | grep -w 'device' | cut -f 1)'
            }
        }
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew connectedAndroidTest'
            }
        }
    }
}
