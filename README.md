## Maven

```bash
mvn exec:java -Dexec.mainClass="wk.Program" \
    -s lib/app/settings.xml \
    -f lib/app/pom.xml

mvn package \
    -s lib/app/settings.xml \
    -f lib/app/pom.xml

mvn deploy \
    -s lib/app/settings.xml \
    -f lib/app/pom.xml
```