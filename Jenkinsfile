pipeline {
    agent any
    stages {
        stage('Pre-Build') {
            steps {
                sh 'echo $ANDROID_HOME'
                sh 'whoami'
                sh 'which adb'
                sh 'export ANDROID_SERIAL=$(adb devices | grep -w "device" | cut -f 1)'
                sh 'cd /Users/caleberios/Development/Loop/indigo-android'
                sh 'pwd'
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
