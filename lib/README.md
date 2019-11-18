## Lib

```bash
cd lib
mvn archetype:generate \
 -DgroupId=wk \
 -DartifactId=hello \
 -Dpackagename=wk \
 -DarchetypeArtifactId=maven-archetype-quickstart \
 -DinteractiveMode=false

```

## Build

```bash
mvn compile -f lib/hello/pom.xml
mvn package -f lib/hello/pom.xml

mvn deploy \
    -s lib/settings.xml \
    -Drepository=github \
    -f lib/hello/pom.xml
```

## Caller

```bash
mvn archetype:generate \
 -DgroupId=wk \
 -DartifactId=caller \
 -Dpackagename=wk \
 -DarchetypeArtifactId=maven-archetype-quickstart \
 -DinteractiveMode=false

mvn clean -f lib/caller/pom.xml
mvn compile -f lib/caller/pom.xml
mvn exec:java -Dexec.mainClass="wk.App2" -f lib/caller/pom.xml

rm -rf ~/.m2/repository/wk
rm -rf ~/.m2/repository/wk-j

mvn clean install -U \
    -f lib/caller/pom.xml \
    -s lib/settings.xml
```

## Issues

```
https://maven.pkg.github.com/wk-j/maven-packages/wk/hello/1.0-snapshot/hello-1.0-snapshot.pom
File "hello-1.0-snapshot.pom" does not exist in Maven package "wk.hello" under owner "wk-j"
```