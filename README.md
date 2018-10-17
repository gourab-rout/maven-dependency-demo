# maven-dependency-demo

This POC demonstrates how to add a mule project as a dependency to another project.
As a result the flows, property files, pom.xml of one application can be resused in the other applications.

## Requirement
   1. Maven
   2. Local Maven repository or Artifactory or Nexus
   3. Download the Mule utility App from https://github.com/indira-mallick/common-utils  which needs to be 
      added as a dependency in other App.

## Build/Install Util App

   1. First download the util project from https://github.com/indira-mallick/common-utils      
   2. Following section in the pom.xml is required to add as dependency.The packaging type should be jar instead of zip/mule. 
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/config-xml.png)	  
   3. Open the terminal and navigate to pom.xml location of the project. Run the command ```mvn clean install```   
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/Build.PNG)	      
   4. On successful installation, the package(jar) is available into the local repository, for use as a dependency 
      in other projects locally 
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/Install.PNG)  
## Adding Dependency in Main App
   
   1. After the util app is successfully installed to local maven repo/ artefactory, it should be added as dependency
      in the pom.xml of Main App.
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/dep.PNG)   
   2. To import the flows of util app following entry needs to be added in the xml.
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/flow.PNG)	  
      By this all the flows, connections can be reused
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/configCopy.png)   
   3. To make pom.xml of utility App as parent pom of Main App
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/maven/parent.png)	  
      
## References
http://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html#Lifecycle_Reference
