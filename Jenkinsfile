node {
	stage('Build') {
	}
	stage('Performance Tests') {
		JMeterTestviaTaurus: {
			sh 'bzt taurus.yaml -report'
		}}
	stage('Deploy') {
	}	
}
