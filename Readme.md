### Microservices BOM

Realease Build

## Git Realease Plugin How to
Release plugin

Test the release using dryRun
> - mvn release:prepare -DdryRun=true

Clean files produced from dryRun
> - mvn release:clean

Prepare the release  
> - mvn release:prepare

Rollback: if you want to reject the release before perform
> - mvn release:rollback

Sure you want the release so Perform it now  
> - mvn release:perform

#### Problems with Git tag exits so
- git tag  

to list all tags, then delete the not desired tag
- git tag --delete [TAG_NAME]

#### POM
Add the scm tag to pom.xml

    <scm>
        <developerConnection>scm:git:https://github.com/mambarek/microservices-bom.git</developerConnection>
        <url>https://github.com/mambarek/microservices-bom</url>
    </scm>
    
#### Release Rollback
- mvn release:rollback

you have to delete the released Tag from your scm. maybe not deleted with the release Plugin

### Jenkins / maven

The local Nexus Repos are defined in ~/.m2/settings.xml

this would not be recognized from Jenkins. Jenkins search for artifacts in the maven central. We have to define them in MAVEN_HOME/config/settings.xml


Test for git push 
    

