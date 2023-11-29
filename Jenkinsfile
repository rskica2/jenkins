node {
	stage('Build') {
	}
	stage('Performance Tests') {
	parallel {
		JMeterTest: {
			bat 'bzt taurus.yaml -report'
		},
		Analysis: {
			sleep 60
		}
	}}
	stage('Deploy') {
	}	
}
