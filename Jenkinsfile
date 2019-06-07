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
		fileOperations {
            		//fileCreateOperation(String fileName, String fileContent)
            		fileCopyOperation(*.pl, , /home/ranjeet/Perl_Project, )
            		//fileDeleteOperation(String includes, String excludes)
            		//fileDownloadOperation(String url, String userName, String password, String targetLocation, String targetFileName)
            		//fileJoinOperation(String sourceFile, String targetFile)
            		//filePropertiesToJsonOperation(String sourceFile, String targetFile)
            		//fileTransformOperation(String includes, String excludes)
            		//fileUnTarOperation(String filePath, String targetLocation, boolean isGZIP)
            		//fileUnZipOperation(String filePath, String targetLocation)
            		//folderCopyOperation(String sourceFolderPath, String destinationFolderPath)
            		//folderCreateOperation(String folderPath)
            		//folderDeleteOperation(String folderPath)
            		//fileRenameOperation(String source, String destination)
            		//folderRenameOperation(String source, String destination)
        	}
                echo 'Finished'
            }
        }
    }
}
