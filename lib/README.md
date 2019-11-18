## Lib

```bash
cd lib
mvn archetype:generate \
 -DgroupId=wk \
 -DartifactId=hello \
 -Dpackagename=wk \
 -DarchetypeArtifactId=maven-archetype-quickstart \
 -DinteractiveMode=false

echo (pwd)/lib
```

## Build

```bash
mvn compile -f lib/hello/pom.xml
mvn package -f lib/hello/pom.xml

mvn deploy \
    -s settings.xml \
    -Drepository=github \
    -f lib/hello/pom.xml
```