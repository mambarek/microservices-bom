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
in maven local setting.xml add 
    <server>
        <id>ubuntu-server</id>
        <username>mmbarek</username>
        <password>mmbarek</password>
    </server>
    
    
Add the scm tag to pom.xml

    <scm>
        <developerConnection>scm:git:http://ubuntu-server:7990/scm/ema/microservices-bom.git</developerConnection>
        <url>http://ubuntu-server:7990/scm/ema/microservices-bom</url>
    </scm>
    
    
this is not working due to ssh problem so what working is this

    <scm>
        <!--<connection>scm:git:ssh://git@ubuntu-server:7999/ema/microservices-bom.git</connection>-->
        <!--<developerConnection>scm:git:ssh://git@ubuntu-server:7999/ema/microservices-bom.git</developerConnection>-->
        <developerConnection>scm:git:http://mmbarek:mmbarek@ubuntu-server:7990/scm/ema/microservices-bom.git
        </developerConnection>
        <url>http://ubuntu-server:7990/scm/ema/microservices-bom</url>
        <tag>microservices-bom-1.6</tag>
    </scm>    
    
#### Release Rollback
- mvn release:rollback

you have to delete the released Tag from your scm. maybe not deleted with the release Plugin

### Jenkins / maven

The local Nexus Repos are defined in ~/.m2/settings.xml

this would not be recognized from Jenkins. Jenkins search for artifacts in the maven central. We have to define them in MAVEN_HOME/config/settings.xml

    

