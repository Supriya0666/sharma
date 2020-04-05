pipeline {

    agent any
	tools{
		jdk 'jdk1.8.0_241'
		maven 'apache-maven-3.6.3'
	}
	
	environment{
		JAVA_HOME ="C:/Program Files/Java/jdk1.8.0_241"
		 MAVEN_HOME ="C:/Program Files/apache-maven-3.6.3"
	}
	
    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://gitlab.com/ssharma1196/awsome.git"
            }
    	}
    	
	stage ('Build') {
	    steps {
		        bat 'mvn -Dmaven.test.failure.ignore=true clean install'
		}
	}
	
	stage ('Deploy'){
	    steps {
		bat 'xcopy /y "C:/Program Files (x86)/Jenkins/workspace/pipe2/Sample.war" "C:/Users/supriya/apache-tomcat-8.5.53/webapps"'
		bat '"C:/Users/supriya/apache-tomcat-8.5.53/bin/startup.bat"'
		}
	}
	}
	}
