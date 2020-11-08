node{

	def mavenHome = tool name: "Maven363"
	stage('CheckOutCode')
	{
		git branch: 'main',
		credentialsId: 'e68ed7ed-63df-4110-b355-dc0fee0e4248',
		url: 'https://github.com/sowmyas9/maven-web-application.git'
	}
	stage('Build')
	{
		bat "mvn -B clean package"
	}
	stage('SonarQubeReport')
	{
		withSonarQubeEnv('MySonar') {
			bat "mvn sonar:sonar"
		}
	}
} 
