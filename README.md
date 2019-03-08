# Demo packaging process

## Prerequisites

Project relies on private Artifactory.
 

`ext` uses [Maven Assembly Plugin](http://maven.apache.org/plugins/maven-assembly-plugin/usage.html) to construct a jar file with classes and zip file with resources that are deployed to `Artifactory`.

`distribubtion` uses [Maven Dependency Plugij](http://maven.apache.org/plugins/maven-dependency-plugin/examples/copying-artifacts.html) to release artifacts distributed by `ext` module using following structure.

```
|____release
| |____bin
| | |____start.sh
| |____config
| | |____config.yml
| |____data
| | |____.db
| |____lib
| | |____ext-1.0-SNAPSHOT.jar
```

## Release resources order

Order of resources overlay is defined in `distribution` module pom.xml file.

```
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-dependency-plugin</artifactId>
...
            <configuration>
                <outputDirectory>${project.build.directory}/release</outputDirectory>
                <includeTypes>zip</includeTypes>
                <includeArtifactIds>ext-2,ext</includeArtifactIds>
            </configuration>
...
</plugin>
```