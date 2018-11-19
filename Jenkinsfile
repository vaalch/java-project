pipeline{
	agent any
	
stages{
	stage('Build'){
		steps{
			sh 'ant'
			sh 'ant -f build.xml -v'
			}
		}
	stage('Test'){
	steps{
		sh 'ant'
		sh 'ant -f test.xml -v'
	junit 'reports/result.xml'
	}
	}
	stage('Deploy'){
		steps{
			sh 'ant'
			sh 'ant -aws s3 -lib /var/jenkins_home/workspace/java-pipeline/dist/rectangle-*.jar s3://github.com-vaalch-javaproject/rectangle'  
		}
	}
 }
}
