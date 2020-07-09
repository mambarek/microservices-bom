### Microservices BOM

Realease Build

mvn release:prepare
mvn release:perform

## Git issues
Release plugin

Test the release using dryRun
> - mvn release:prepare -DdryRun=true

Clean files produced from dryRun
> - mvn release:clean

Prepare the release  
> - mvn release:prepare

Perform it now  
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
    <tag>HEAD</tag>
    
#### Release Rollback
- mvn release:rollback

you have to delete the released Tag from your scm. maybe not deleted with th release Plugin    

