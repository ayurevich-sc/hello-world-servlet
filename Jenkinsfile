node 
  {
	  withEnv(["path_to_artifact=${'/home/andrey/.jenkins/jobs/test_pipeline/workspace/artifacts/artifacts/repo/target'}", "tomcat_root=${'/home/andrey/sources/apache-tomcat-7.0.73/webapps/ROOT'}"]) 
	  {
    stage("remove root")
	{
		sh "find ${tomcat_root} -delete "
		sh "mkdir ${tomcat_root}"
	}
    stage('copy')
	{
		sh 'cp ${path_to_artifact}/helloworld.war ${tomcat_root}'
	}
	stage('extract')
	{
	    sh "unzip ${tomcat_root}/helloworld.war -d ${tomcat_root}"
	}
	  } 
  }
