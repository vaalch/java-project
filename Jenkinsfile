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
			sh 'aws s3 cp reports/result/rectangle-*.jar s3://github.com-vaalch-javaproject'
		}
	}
	post{
		always {
			archiveArtifacts artifacts: 'reports/result/rectangle-*.jar, fingerprint: true
		}
	}
 }
}
