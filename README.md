## Maven

```bash
mvn exec:java -Dexec.mainClass="wk.Program"
mvn package

mvn deploy -s settings.xml \
    -Dregistry=https://maven.pkg.github.com/wk-j

mvn deploy \
    -s settings.xml \
    -Drepository=github
```