FMPP Maven Plugin
===

This is largely inspired by https://github.com/dremio/dremio-oss/tree/master/tools/fmpp-maven-plugin.

Provide a context free FMPP Maven Plugin.

Example usage:
```
      <plugin>
        <groupId>org.walterddr</groupId>
        <artifactId>fmpp-maven-plugin</artifactId>
        <version>${project.version}</version>
        <executions>
          <execution>
            <id>generate-fmpp-sources</id>
            <phase>generate-sources</phase>
            <goals>
              <goal>generate</goal>
            </goals>
            <configuration>
              <config>${project.basedir}/src/main/codegen/config.fmpp</config>
              <output>${project.build.directory}/generated-sources/fmpp</output>
              <templates>${project.build.directory}/codegen/templates</templates>
              <data>tdd(${project.basedir}/src/main/codegen/config.fmpp), default:tdd(${project.build.directory}/codegen/default_config.fmpp)</data>
            </configuration>
          </execution>
        </executions>
      </plugin>
```
