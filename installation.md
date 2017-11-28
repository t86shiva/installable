Jenkins Installation:
	Pre-requisite: JAVA 8 while installing 2.X >
		       JAVA 7 < 2.X Version
Installation on Ubuntu:
	1. Create a repository from where Debian packages can be downloaded.
		wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
	2. Add below line
		sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
	3. Update the package
		sudo apt-get update
	4. Install the package
		sudo apt-get install jenkins
	5. Validate whether the service is installed
		sudo service jenkins { status | start | stop | restart }
		sudo systemctl status jenkins 
	6. Once the service is started, login using
		Browser --> http://localhost:8080
		And follow the instruction.

Installation on Centos:
	1. Create a repository
		sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo
	2. Run below command
		sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
	3. Run yum package
		sudo yum install jenkins
	4. Validate whether the service is installed
		sudo service jenkins { status | start | stop | restart }
		sudo systemctl status jenkins 
	5. Once the service is started, login using
		Browser --> http://localhost:8080
		And follow the instruction.

Installing manually:
	1. Downlaod the Jenkins war file.
		wget https://updates.jenkins-ci.org/download/war/2.92/jenkins.war
	2. Use Java command to run the jar file
		nohup java -Dhudson.model.UsageStatistics.disabled=true -Dgroovy.use.classvalue=true -Djenkins.slaves.NioChannelSelector.disabled=true -Dhava.io.tmpdir="/home/ec2-user/jenkins/tmp" -Djsse.enableSNIExtension=false -Dhudson.model.ParametersAction.keepUndefinedParameters=true -Xms6144m -Xmx14448m -XX:PermSize=256m -XX:MarPermSize=1024m -XX:MinHeapFreeRatio=40 -XX:MaxHeapFreeRatio=70 -XX:+UseParallelGC -jar "/home/ec2-user/jenkins/" JENKINS_ARGS="-webroot=/home/ec2-user/jenkins/ --httpPort=8080" >> "/home/ec2-user/jenkins/log/cmd.log" 2>&1&

---------------------------------------------------------------------------------------------------------

GIT Installation:

Installation on Ubuntu or Centos:
	1. Ubuntu
		sudo apt-get install git
	2. Centos
		sudo yum install git
Validation:
	1. Ubuntu or Centos
		which git
		git --version
Expected output:
	1. --> /usr/bin/git
	2. --> git 2.7
		

		
