<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	<modelVersion>4.0.0</modelVersion>
	
	<groupId>com.mt</groupId>
	<artifactId>maven-web-application</artifactId>
	<packaging>war</packaging>
	<version>0.0.1-SNAPSHOT</version>
	
	<name>maven-web-application</name>

	<description>Maven Web Project for Java Project</description>

	<organization>
		<name>Landmark Technologies</name>
		<url>http://landmarktechnologies.com/</url>
	</organization>

	<properties>
		<jdk.version>1.8</jdk.version>
		<spring.version>5.1.2.RELEASE</spring.version>
		<junit.version>4.11</junit.version>
		<log4j.version>1.2.17</log4j.version>
		<sonar.host.url>http:172.31.86.141:9000/</sonar.host.url>
		<sonar.login>admin</sonar.login>
		<sonar.password>admin</sonar.password>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>

	</properties>

	<dependencies>
		
		<dependency>
			<groupId>org.json</groupId>
			<artifactId>json</artifactId>
			<version>20160212</version>
		</dependency>
		
		<!-- test dependencies -->
		<dependency>
			<groupId>junit</groupId>
			<artifactId>junit</artifactId>
			<version>3.8.1</version>
			<scope>test</scope>
		</dependency>

		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>javax.servlet-api</artifactId>
			<version>3.1.0</version>
			<scope>provided</scope>
		</dependency>

		<dependency>
			<groupId>org.mockito</groupId>
			<artifactId>mockito-core</artifactId>
			<version>1.9.5</version>
			<scope>test</scope>
		</dependency>

		<!-- compile dependencies -->

		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-core</artifactId>
			<version>${spring.version}</version>
		</dependency>
		<dependency>
    		<groupId>org.springframework</groupId>
    		<artifactId>spring-web</artifactId>
    		<version>${spring.version}</version>
  		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-webmvc</artifactId>
			<version>${spring.version}</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>${spring.version}</version>
		</dependency>
		
		<!-- provided dependencies -->

		<dependency>
			<groupId>javax.servlet</groupId>
			<artifactId>javax.servlet-api</artifactId>
			<version>3.1.0</version>
			<scope>provided</scope>
		</dependency>
		
	</dependencies>
	
	<distributionManagement>
	    <repository>
	      <id>nexus</id>
	      <name>Landmark Technologies Releases Nexus Repository</name>
	      <url>http://54.234.19.165:8081/repository/bmo-repo/</url>
	    </repository>
	    
	    <snapshotRepository>
	      <id>nexus</id>
	      <name>Landmark Technologies Snapshot Nexus Repository </name>
	      <url>http://54.234.19.165:8081/repository/bmo-snap/</url>
	    </snapshotRepository>
	    
	</distributionManagement>
	
	<build>
		<finalName>maven-web-app</finalName>
		
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>3.3</version>
				<configuration>
					<source>${jdk.version}</source>
					<target>${jdk.version}</target>
				</configuration>
			</plugin>

			<plugin>
				<groupId>org.eclipse.jetty</groupId>
				<artifactId>jetty-maven-plugin</artifactId>
				<version>9.2.11.v20150529</version>
				<configuration>
					<scanIntervalSeconds>10</scanIntervalSeconds>
					<webApp>
						<contextPath>/maven-web-application</contextPath>
					</webApp>
				</configuration>
			</plugin>

			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-eclipse-plugin</artifactId>
				<version>2.9</version>
				<configuration>
					<downloadSources>true</downloadSources>
					<downloadJavadocs>true</downloadJavadocs>
					<wtpversion>2.0</wtpversion>
					<wtpContextName>maven-web-application</wtpContextName>
				</configuration>
			</plugin>
			
</plugins>
	</build>
	
	
</project>
