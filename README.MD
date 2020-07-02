# Introduction

This is an example project to include system scope jars in the build.

In this example, I have a third-party jar placed in the folder called "external". This folder is seen under project base directory.

Now, when you do build with the command "mvn clean install"; the third party jar will be included in the final jar file. 

# How to include third party jars that is not available in maven repo?

> Add a dependecny with the scope as system. The system path should point to the jar on the file system.

```
		<dependency>
			<groupId>com.pmalla</groupId>
			<artifactId>work</artifactId>
			<version>1.0</version>
			<scope>system</scope>
			<systemPath>${project.basedir}/external/work-1.0.jar</systemPath>
		</dependency>
```

# How to include system scope jars in the maven build?
> The plugin called "pring-boot-maven-plugin" should define the configuration to inclide system scope jars

```
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<configuration>
					<includeSystemScope>true</includeSystemScope>
				</configuration>
			</plugin>
		</plugins>
	</build>
```
