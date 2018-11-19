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
			sh 'aws s3 cp /workspace/java-pipeline/dist/rectangle-55.jar s3://github.com-vaalch-javaproject/rectangle'  
		}
	}
 }
}
