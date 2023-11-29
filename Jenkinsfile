node {
    stage('Clone sources') {
        git url: 'https://github.com/rskica2/jenkins.git'
    }
	stage('Build') {
	}
	stage('Performance tests') {
		JMeterTestviaTaurus: {
			sh 'bzt taurus.yaml -report'
		}}
	stage('Deploy') {
	}	
}
