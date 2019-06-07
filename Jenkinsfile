pipeline {
    agent any
    
    stages {
        stage ('Build') {
            steps {
                //sh "rm -rf Perl-Ranjeet*"
                sh "git clone https://github.com/donfir/Perl.git"
            }
        }
        stage ('Compile Stage') {
            steps {
                dir('/var/lib/jenkins/workspace/Perl-Ranjeet_master/Perl/') {
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
                //dir('/var/lib/jenkins/workspace/Perl-Ranjeet_master/Perl/') {
                //   sh 'cp -p test.pl /home/ranjeet/Perl_Project'
                //   sh 'cp -p hello.pl /home/ranjeet/Perl_Project'
                //}
		script {
            		fileOperations([
                    		folderCopyOperation(
                            		destinationFolderPath: '/home/ranjeet/Perl_Project/',
                            		sourceFolderPath: '/var/lib/jenkins/workspace/Perl-Ranjeet_master/Perl/')
            		])
        	}
                echo 'Finished'
            }
        }
    }
}
