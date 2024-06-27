# Learning pom.xml file

## NEXUS
1. for Nexus we are configuring the URL in ***distribution management*** tag
2. we configure the credentials in the setting.xml in maven home directory in the conf directory under the ***server*** tag ![image](https://github.com/bhargavsp/maven/assets/45779321/202d92a8-4187-401c-9645-f4f2c6f1d2c2)
3. after configuring that we use the mvn deploy it deploys the build artifact into the sonatype nexus repository ![image](https://github.com/bhargavsp/maven/assets/45779321/4a2bf322-5e34-40f9-afd2-93f3c3264c5b)



## SONARQUBE
1. For sonarQube we are configuring both the URL and CREDENTIALS in the ***propeties*** tag <br/> ![image](https://github.com/bhargavsp/maven/assets/45779321/f7a7d737-da05-4699-88d6-c49b432e9bb4)
2. for the credentials we also give the sonar token instead of username and password <br/> ![image](https://github.com/bhargavsp/maven/assets/45779321/fd99ad2c-1a2d-46e0-b12c-2b5bc5e735de)
3.  to run the sonar in maven **`mvn sonar:sonar`** first sonar represents the plugin name and second sonar after colan represents the goal name
