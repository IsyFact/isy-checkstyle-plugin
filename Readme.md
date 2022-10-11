# isy-checkstyle-config

## Usage

### Integration by maven parent

`isy-checkstyle-config` is already configured if using one of the following Maven parents.

|Module|Min. Version|
|---|---|
|`isyfact-standards`|2.2.0-SNAPSHOT |
|`isyfact-erweiterungen`| 2.1.1, 1.8.2|

### Integration as plugin configuration

The following example shows how `isy-checkstyle-config` can be integrated using the `maven-checkstyle-plugin` plugin.

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-checkstyle-plugin</artifactId>
            <version>3.1.1</version>
            <configuration>
                <configLocation>checkstyle.config.xml</configLocation>
                <encoding>UTF-8</encoding>
                <consoleOutput>true</consoleOutput>
                <failsOnError>true</failsOnError>
                <linkXRef>false</linkXRef>
            </configuration>
            <dependencies>
                <dependency>
                    <groupId>de.bund.bva.isyfact</groupId>
                    <artifactId>isy-checkstyle-config</artifactId>
                    <version>0.1.0</version>
                </dependency>
            </dependencies>
            <executions>
                <execution>
                    <id>validate</id>
                    <phase>validate</phase>
                    <goals>
                        <goal>check</goal>
                    </goals>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```
