node {
	stage('Build') {
	}
	stage('Performance Tests') {
	    git url: 'https://github.com/rskica2/jenkins.git'
		JMeterTestviaTaurus: {
			sh 'bzt taurus.yaml -report'
		}}
	stage('Deploy') {
	}	
}
