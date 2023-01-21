pipeline {
	agent any
	environment {
	def git_branch = 'master'
	def git_url = 'https://github.com/rishikant4/devops.git'
	
	def mvntest = 'mvn test '
	def mvnpackage = 'mvn clean install'
	
	def utest_url = 'target/surefire-reports/**/*.xml'
		
	def sonar_cred = 'sonar'
        def code_analysis = 'mvn clean install sonar:sonar'
		
	def nex_cred = 'nexus'
        def grp_ID = 'com.example'
        def nex_url = '13.232.148.141:8081'
        def nex_ver = 'nexus3'
        def proto = 'http'
	}
	stages {
	stage('Git Checkout') {
	steps {
	script {
	git branch: "${git_branch}", url: "${git_url}"
	echo 'Git Checkout Completed'
	}
	}
	} 
	stage('Maven Build') {
	steps {
	sh "${env.mvnpackage}"
	echo 'Maven Build Completed'
	}
	}
  }
}
