node 
  {
	  withEnv(['path_to_artifact=/home/andrey/.jenkins/jobs/test_pipeline/workspace/artifacts/artifacts/repo/target, tomcat_root=/home/andrey/sources/apache-tomcat-7.0.73/webapps/ROOT']) 
	  {
    stage("remove root")
	{
		sh "find ${tomcat_root} -delete"
	}
    stage('copy & unzip')
	{
		copyArtifacts filter: '/home/andrey/.jenkins/jobs/test_pipeline/workspace/artifacts/artifacts/repo/target/helloworld.war', fingerprintArtifacts: true, projectName: 'test_pipeline', selector: lastSuccessful(), target: '/home/andrey/sources/apache-tomcat-7.0.73/webapps/ROOT'
		sh "jar -xf ${tomcat_root}/helloworld.war"
		
	}
	  } 
  }
