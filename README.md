# Demo packaging process
 

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