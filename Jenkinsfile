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
			sh 'aws s3 cp rectangle-*.jar/master s3://github.com-vaalch-javaproject'
		}
	}
 }
}
