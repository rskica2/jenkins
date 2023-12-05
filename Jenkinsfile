node {
  environment {
	ENV = "${params.env}"
  }	
  stage('Clone sources for Performance test') {
  	git url: 'https://github.com/rskica2/jenkins.git'
  }
  stage('Build') {
	  step([$class: 'WsCleanup'])
  }	
  stage('Performance tests') { 
  	sh "mv config/${env.ENV}.yaml taurus.yaml" // move the selected environment configuration to config.yaml
	JMeterTestviaTaurus: {
		sh "bzt -o modules.jmeter.properties.threadNumber=${env.threadNumber} -o modules.jmeter.properties.duration=${env.duration} /var/lib/jenkins/workspace/taurus-github-poc/taurus.yaml"
	}
        // archive artifacts only from the application directory
        archiveArtifacts artifacts: "**/junit-result-passfail.xml", fingerprint: true
	archiveArtifacts artifacts: "**/perf_resut_csv.csv", fingerprint: true  
	archiveArtifacts artifacts: "**/internet-serwis-cabp.jtl", fingerprint: true    
	perfReport "internet-serwis-cabp.jtl" 
	// performanceReport parsers: [[$class: 'JMeterParser', glob: "jmeter_scripts\\${jmeterTestFile}_results.jtl"]], relativeFailedThresholdNegative: 1.2, relativeFailedThresholdPositive: 1.89, relativeUnstableThresholdNegative: 1.8, relativeUnstableThresholdPositive: 1.5
  }
  stage('Deploy') {
  }		
}
