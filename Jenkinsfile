anode {
  environment {
    ENV = "${params.env}"
  }

    stage('Clone sources') {
        git url: 'https://github.com/rskica2/jenkins.git'
    }
	stage('Build') {
	}
	stage('Performance tests') {
		sh "mv config/${env.ENV}.yaml taurus.yaml" // move the selected environment configuration to config.yaml
		JMeterTestviaTaurus: {
			sh 'bzt -o scenario.simple.properties.threadNumber=${env.threadNumber} /var/lib/jenkins/workspace/taurus-github-poc/taurus.yaml'
		}}
	stage('Deploy') {
	}		
}
