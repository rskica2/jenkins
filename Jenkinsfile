node {
  environment {
    ENV = "${params.env}".toLowerCase()
  }

    stage('Clone sources') {
        git url: 'https://github.com/rskica2/jenkins.git'
    }
	stage('Build') {
	}
	stage('Performance tests') {
		sh "mv config/${env.ENV}.yaml taurus.yaml" // move the selected environment configuration to config.yaml
		JMeterTestviaTaurus: {
			sh 'bzt /var/lib/jenkins/workspace/taurus-github-poc/taurus.yaml'
		}}
	stage('Deploy') {
	}		
}
