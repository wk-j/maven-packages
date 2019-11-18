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
    -s settings.xml \
    -Drepository=github \
    -f lib/hello/pom.xml
```

```
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

mvn clean install -U \
    -f lib/caller/pom.xml \
    -s settings.xml
```