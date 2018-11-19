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
			sh 'aws s3 cp /var/jenkins_home/plugins/build-environment/WEB-INF/lib/classes.jar s3://github.com-vaalch-javaproject'  
		}
	}
 }
}
