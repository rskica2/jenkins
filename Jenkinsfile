node {
  environment {
	ENV = "${params.env}"
  }
  stage('Build') {
  }
  stage('Clone sources for Performance test') {
  	git url: 'https://github.com/rskica2/jenkins.git'
  }
  stage('Performance tests') {
  	sh "mv config/${env.ENV}.yaml taurus.yaml" // move the selected environment configuration to config.yaml
	bzt params: "bzt -o modules.jmeter.properties.num_threads=${env.num_threads} -o modules.jmeter.properties.duration=${env.duration}"  
	JMeterTestviaTaurus: {
		sh 'bzt /var/lib/jenkins/workspace/taurus-github-poc/taurus.yaml'
	}}
  stage('Deploy') {
  }		
}
