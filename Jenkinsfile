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
			s3Upload(file:'rectangle-*.jar', 'bucket:github.com-vaalch-javaproject', path:'path/rectangle-*.jar')
		}
	}
 }
}
