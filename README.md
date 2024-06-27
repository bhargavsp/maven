# maven

It is a build tool, other thean Maven we have some other build tools as well

| Language | Build tool |
| :---: | :---: |
| **`JAVA`** | Ant/Maven/gradle |ant is a legacy tool, so we are not using it; Gradle is a advanced buuild tool, so we have greate support for the Maven we are using it rapidly in the JAVA  |
| **`.Net`** | Nant/Ms Build |
| **`Python`** | PyBuilder |
| **`Ruby`** | Rake |

*Maven* is a open source java based build tool

Build: It is a process of creating the packages

## Using Java we can create different type of tha pplications
1. Standalone applications: jar --> jar Archive, java code
2. web applications: War --> web Archive, java code + web content (html/css/js/images/xml/jsp)
3. Enterprise applciations: ear --> enterprise archive, which contains multiple modules (web applications, standalone applciations and more....) all together it is a enterprise application

## can we run a JAR file?
Yes we can in the command line, by using the following commands
![image](https://github.com/bhargavsp/maven/assets/45779321/e57d66a0-886c-4238-878e-7160f2111315)

## When we use the Binary file and source file while downloading the maven?
Binaray file - for packages <br/>
source file - enhance on top of the exisiting features, we use the source file.

## maven directory structure
As maven is not a **`executable software`**. we want to extract an use it. the folders in the maven are
1. boot: jar files
2. bin: binary files 
3. conf: It contains all the configurations. Ex: settings.xml
4. lib: all the dependency libraries jar files

## Maven configuration 
java is the Prerequisites 
JDK is Prerequisites
| Package |  Link |
| :---: | :---: |
| Installing java 11 on amazon linux machine | https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/amazon-linux-install.html |
| Install maven | https://maven.apache.org/download.cgi *and* https://mithuntechnologies-devops.blogspot.com/search/label/Maven |
install wget and unzip in OPT directpory | `yum install wget unzip -y`
Set the class path/Environmental Variable For Specific User | **`vi ~/.bash_profile`** and add these 2 lines **`export M2_HOME=/opt/apache-maven-3.9.5`** and **`export PATH=$PATH:$M2_HOME/bin`**
source the profile | `source ~/.bash_profile`
Set the class path/Environmental Variable For All Users | **`vi /etc/profile`** and **`export M2_HOME=/apache-maven-3.9.5`** and **`export PATH=$PATH:$M2_HOME/bin`**
Check the Maven version | mvn -version

## build files in the different Build tools
| Build tool | filename |
| :---: | :---: |
| Ant | build.xml |
| Maven | pom.xml |
| gradle | build.gradle |

**`we can also create an our own build file name according to the project bobwebapp.xml`**

## Sample conten in the pom.xml file:
| name | Notation |
| :---: | :---: |
| **`root tag or parent tag`** | `<project> </project>` |

XML - extensabel markup language

## command used in maven 
| command | Usage |
| :---: | :---: |
|mvn compile|it compiles the source code and unit test cases|
|**`mvn package`**| use to build the java source code |
|mvn test| used to run all the unit test cases|
|mvn install| to stores the artifact to the local repo|
|mvn deploy|it stores the artifact to the remote repo|
|mvn clean package -Dskiptests|ignores the unit test cases by running and packages the source code |
|mvn clean package -Dmaven.test.skip=true|| skips the compile and running of the unit test cases |

## what happens whe we run the mvn pakcage command
it checks all the dependencies in the .xml file and downloads them from the `maven repositories`
1. maven local repo: It contains all our project dependencies, locally ex: ~/.m2/repository 
2. maven central repo: It is maintened by the maven community, if our project dependency are not found in the local repository then it fetches an downloads the dependency to the local and from there the maven takes
3. remote repo: companies maintain the remote repository by there own, within the company, so thet are found in our company server.

## The developer writes the following files and give the devops for the deployment
1. source code
2. build script
3. unit test cases based on the language

## lifecycles of the maven
|life cycle|goal|
|:---:|:---:|
|clean|clean:It delets the previous build files|
|site|site:It will generates the documentation, isntead of manually generating the documentation, this will create an automatic documentation |
|default|It has many goals <br/> validate: It will validate the project dir structure and check the resource files <br/>, compile <br/>, test, package, install, deploy|

## what is the naming convention that the maven follows for the build artifact?
from the pom.xml it takes the **`artifactid-versionNo.jar`**

## inside the target folder which is creatd after a build package is done?
|folder name |usage|
|:---:|:---:|
|test-classes|stores the .class files of the test cases|
|classes| contains all the sources .class files|

## change the maven default local repository path
1. create a new repository where you want to save the new reposotory path
2. set the path <localRepository>newpath<localRepository/>
3. go to the config/setting.xml file and search for the <localRepository> and paste the new path and save it
4. Now, if you run a build the ~/.m2/maven is replcaed by new path and hte build files are save in the new path


## how to comment in XML
`<!--      -->` this is the notation we are used to comment in the XML

## can we create an own artifact name after build rather than default name
yes, we can in the pom.xml, change the `<finalName>ownName<finalName/>` tag

## requirement to create and ear artifact?
we should have atleast 1war file and multiple jar files for creating an ear artifact. In the parent pom.xml we see the modules tag, there we cn see all the modules we have for this ear application

## how to clean package for only one module in the whole ear package
mvn clean package -pl MavenEnterpriseApp-web. Here `pl` is `project list`, `module name` is `MavenEnterpriseApp-web`

## maven configuration steps
|command |usage|
|:---:|:---:|
wget https://dlcdn.apache.org/maven/maven-3/3.9.5/binaries/apache-maven-3.9.5-bin.zip | download maven version in OPT directory
unzip apache-maven-3.9.5-bin.zip | unzip maven
vi ~/.bash_profile | export M2_HOME=/opt/apache-maven-3.9.5 ***and*** export PATH=$PATH:$M2_HOME/bin (for specific user)
source ~/.bash_profile | to restart the bash profile
mvn -version | version

## cloning the java project
|command |usage|
|:---:|:---:|
mkdir projects | login to sudo and create the folder and clone the project from github
https://github.com/MithunTechnologiesDevOps/maven-web-application | sample java web application
rm -r jenkinsfile* | to remove unnecessary files and folders
mvn clean package | to run the build
cd maven/target | the target folder is created once after the build, go to the folder to check the maven.war file 

### what if we want to download the packages from the remote repository?
1. we should configure the remote repository URL in the pom.xml file in the ***repository*** tag
2. still the build cant download the file from remote repository so then we have go to settings.xml file in the conf direcotry in maven home and allow in the mirror tag ![image](https://github.com/bhargavsp/maven/assets/45779321/d9cd155d-4130-4984-9527-e02f40fbdb17)















