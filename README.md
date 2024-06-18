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
2. web applications: War --> web Archive, java code + web content (html/css/js/images/xml)
3. Enterprise applciations: ear --> enterprise archive, which contains multiple modules (web applications, standalone applciations and more....) all together it is a enterprise application

## When we use the Binary file and source file while downloading the maven?
Binaray file - for packages <br/>
source file - enhance on top of the exisiting features, we use the source file.

## maven directory structure
As maven is not a **`executable software`**. we want to extract an use it. the folders in the maven are
1. boot: jar files
2. bin: binary files 
3. conf: It contains all the configurations. Ex: settings.xml
4. lib: all the dependency libraries jar files

## Maven installation: 
java is the Prerequisites 
JDK is Prerequisites
| Package |  Link |
| :---: | :---: |
| Installing java 11 on amazon linux machine | https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/amazon-linux-install.html |
| Install maven | https://mithuntechnologies-devops.blogspot.com/search/label/Maven |

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























