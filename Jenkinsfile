pipeline {
    agent any
    
    stages {
        stage ('Build') {
            steps {
                sh "rm -rf Perl"
                sh "git clone https://github.com/donfir/Perl.git"
            }
        }
        stage ('Compile Stage') {
            steps {
                dir('/var/lib/jenkins/workspace/Perl2/Perl/') {
                   sh 'perl -c test.pl'
		   sh 'perl -c hello.pl'
                }
                echo 'Compile Stage'
            }
        }
        stage ('Test') {
            steps {
                echo 'Test'
                //fileExists '/home/ranjeet/Desktop/www/test.pl'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Finished'
            }
        }
    }
}
