pipeline {
    agent any
    stages {
        stage('Stage_one') {
            steps {
                echo 'Hello World, this is Stage_one'
            }
        }
		stage('Stage_two') {
            steps {
                echo 'Hello World, this is Stage_two'
            }
        }
		stage('Stage_Three') {
            steps {
                echo 'Hello World, this is Stage_Three'
            }
        }
		stage('Stage_Four') {
            steps {
                echo 'Hello World, this is Stage_Four'
            }
        }
		stage('Stage_Five') {
            steps {
                echo 'Hello World, this is Stage_Five'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}