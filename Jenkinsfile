String exitcode='0'

pipeline { 
    agent any 
   
    stages {
        stage('Stage 1') { 
            steps { 
               bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_1.pl"
            }
        }
        stage('Stage 2'){
            steps {
                script
                {
                    if (exitcode!='0')
                    {
                       bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_2.pl"
                    }
                    else
                    {
                        unstable("Stage 2 skipped")
                    }
                }
            }
        }
        stage('Stage 3') {
             steps {
                 catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_3.pl"
                 }
            }
        }
        stage('Stage 4') {
            when{ expression{
                exitcode!='0' 
            }
            }
            steps {
                bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_4.pl"
            }
        }
         stage('Stage 5') {
            steps {
                 warnError('Script failed!') {
                   bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_3.pl"
                }
            }
        }
         stage('Stage 6') {
            steps {
                bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_4.pl"
            }
        }
        stage('Stage parallel check') {
            parallel {
                stage('Stage 7') {
                    steps {
                       bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_5.pl"
                    }
                }
                 stage('Stage 8') {
                    steps {
                       bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_6.pl"
                    }
                }
            }   
        }
         stage('Stage 9') {
            steps {
                bat "perl D:\\jenkins\\Jobs\\Pipeline_examples\\script_4.pl"
            }
        }
    }
}