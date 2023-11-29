node {
    stage('Clone sources') {
        git url: 'https://github.com/rskica2/jenkins.git'
    }
	stage('Build') {
	}
	stage('Performance tests') {
		JMeterTestviaTaurus: {
			sh 'bzt /var/lib/jenkins/workspace/taurus-github-poc/taurus.yaml'
		}}
	stage('Deploy') {
	}	
}