##

การอัปโหลด Maven Artifact ขั้น GitHub Registry

1. สร้างโปรเจคผ่าน Command line

mvn archetype:generate \
 -DgroupId=wk \
 -DartifactId=hello \
 -Dpackagename=wk \
 -DarchetypeArtifactId=maven-archetype-quickstart \
 -DinteractiveMode=false

2.เพิ่มไฟล์ `settings.xml` ให้ใช้ Account ของ GitHub เป็น username  และ Token เป็น password

<settings>
    <servers>
        <server>
            <id>github</id>
            <username>wk-j</username>
            <password>[GitHubToken]</password>
        </server>
    </servers>
</settings>

3. เพิ่ม Tag distributionManagement ในไฟล์ pom.xml โดยให้เปลี่ยน [GitHubAccount] และ [GitHubProject] ให้ตรงกับโปรเจคใน GitHub

    <distributionManagement>
        <repository>
            <id>github</id>
            <name>GitHub OWNER Apache Maven Packages</name>
            <url>https://maven.pkg.github.com/[GitHubAccount]/[GitHubProject]</url>
        </repository>
    </distributionManagement>

4. อัปโหลด Artifact ผ่าน Command line

```
mvn deploy \
    -s settings.xml \
    -Drepository=github \
    -f hello/pom.xm
```