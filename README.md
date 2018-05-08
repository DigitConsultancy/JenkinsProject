# JenkinsProject

1. java -jar jenkins.war --httpPort=9090

   Password : 82c48f3af72c4b1e9f8543da88f8627d

2. All the plugins will get installed in C:\Users\sid\.jenkins

3. Create first admin user:
    Username : sid28gunner@gmail.com
    Password : 
    fullName : sid
    E-mail   : sid28gunner@gmail.com

4. Enable Read only access
   Add new User

5. Clone a java project https://github.com/g0t4/jenkins2-course-spring-boot.git 
   Install maven on windows
       Add M2_HOME and MAVEN_HOME in Windows environment
       Update PATH variable, append Maven bin folder – %M2_HOME%\bin
	   > mvn -version
	   > mvn compile
	   >mvn test
	   >mvn package
	   
	   
6. 	  Create new Jobs -> Build now -> see the console ->C:\Users\sid\.jenkins\workspace\JenkinsFreestyle
       Workspace gets overrideen so you need to keep a history
	   Post Build Process -> Last Successful Artifacts
	   Cleaning up past builds -> mvn clean
	   trend
	   sun cloud storm
	   error in build -> Everything works same -> see the color -> see console
	   Manage jenkins -> reload conf from disk
	   Job -> Config -> build, build, build
	   
7.  Continous Integration
    Pipeline : 
    Email : Mailhog with docker	

 * * * * *
 
node{
stage('checkout')
git 'https://github.com/DigitConsultancy/JenkinsProject.git'
bat 'mvn clean package'
archiveArtifacts 'target/*.jar'
}
