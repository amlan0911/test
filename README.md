<project xmlns="http://maven.apache.org/POM/4.0.0"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.uhc.ei.reportit</groupId>
	<artifactId>Report-It</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<packaging>war</packaging>
	<name>Report It Web</name>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.2.5</version>
		<relativePath /> <!-- lookup parent from repository -->
	</parent>
	<properties>
		<java.version>17</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-api</artifactId>
			<version>2.20.0</version>
		</dependency>
		<dependency>
			<groupId>org.apache.logging.log4j</groupId>
			<artifactId>log4j-core</artifactId>
			<version>2.20.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
			<version>3.2.5</version>
			<exclusions>
				<exclusion>
				    <groupId>org.springframework.boot</groupId>
				    <artifactId>spring-boot-starter-logging</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
		    <groupId>org.springframework.boot</groupId>
		    <artifactId>spring-boot-starter-log4j2</artifactId>
		</dependency>
		<dependency>
			<groupId>org.apache.httpcomponents.client5</groupId>
			<artifactId>httpclient5</artifactId>
			<version>5.2.1</version>
		</dependency>
	<dependency>
		<groupId>org.json</groupId>
		<artifactId>json</artifactId>
		<version>20231013</version>
	</dependency>
		<dependency>
			<groupId>io.netty</groupId>
			<artifactId>netty-resolver-dns-native-macos</artifactId>
			<version>4.1.108.Final</version>
			<scope>runtime</scope>
			<exclusions>
				<exclusion>
					<groupId>io.netty</groupId>
					<artifactId>netty-handler</artifactId>
				</exclusion>
				<exclusion>
					<groupId>io.netty</groupId>
					<artifactId>netty-common</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>io.netty</groupId>
			<artifactId>netty-handler</artifactId>
			<version>4.1.118.Final</version>
		</dependency>
		<dependency>
			<groupId>io.netty</groupId>
			<artifactId>netty-common</artifactId>
			<version>4.1.118.Final</version>
		</dependency>
		<dependency>
			<groupId>com.microsoft.sqlserver</groupId>
			<artifactId>mssql-jdbc</artifactId>
			<version>9.4.0.jre8</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-web</artifactId>
			<version>6.1.12</version>
		</dependency>
		<dependency>
			<groupId>jakarta.xml.bind</groupId>
			<artifactId>jakarta.xml.bind-api</artifactId>
			<version>4.0.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-test</artifactId>
		</dependency>
		<dependency>
			<groupId>org.apache.httpcomponents</groupId>
			<artifactId>httpcore</artifactId>
		</dependency>
		<dependency>
			<groupId>net.sourceforge.jtds</groupId>
			<artifactId>jtds</artifactId>
			<scope>runtime</scope>
		</dependency>
		<dependency>
			<groupId>com.zaxxer</groupId>
			<artifactId>HikariCP</artifactId>
		</dependency>
		<dependency>
			<groupId>jakarta.servlet.jsp.jstl</groupId>
			<artifactId>jakarta.servlet.jsp.jstl-api</artifactId>
			<version>3.0.0</version>
		</dependency>
		<dependency>
			<groupId>org.glassfish.web</groupId>
			<artifactId>jakarta.servlet.jsp.jstl</artifactId>
			<version>2.0.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-devtools</artifactId>
			<scope>runtime</scope>
			<optional>true</optional>
		</dependency>
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
<!--			<version>11.0.2</version>-->
		</dependency>
		<dependency>
			<groupId>org.apache.commons</groupId>
			<artifactId>commons-lang3</artifactId>
			<version>3.12.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-data-jpa</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springdoc</groupId>
			<artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
			<version>2.2.0</version>
		</dependency>
		<dependency>
			<groupId>io.swagger</groupId>
			<artifactId>swagger-models</artifactId>
			<version>1.5.20</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>runtime</scope>
			<exclusions>
				<exclusion>
					<groupId>org.xmlunit</groupId>
					<artifactId>xmlunit-cor</artifactId>
				</exclusion>
				<exclusion>
					<groupId>net.minidev</groupId>
					<artifactId>json-smart</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>net.minidev</groupId>
			<artifactId>json-smart</artifactId>
			<version>2.5.2</version>
		</dependency>
		<dependency>
			<groupId>org.xmlunit</groupId>
			<artifactId>xmlunit-core</artifactId>
			<version>2.10.0</version>
			<scope>test</scope>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-mail</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webflux</artifactId>
			<version>3.2.6</version>
			<exclusions>
				<exclusion>
					<groupId>org.springframework</groupId>
					<artifactId>spring-webflux</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-webflux</artifactId>
			<version>6.1.14</version>
		</dependency>
		<dependency>
			<groupId>com.google.code.gson</groupId>
			<artifactId>gson</artifactId>
		</dependency>
		<dependency>
			<groupId>jakarta.persistence</groupId>
			<artifactId>jakarta.persistence-api</artifactId>
			<version>3.1.0</version>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-webmvc</artifactId>
			<version>6.1.14</version>
			<exclusions>
				<exclusion>
					<groupId>org.springframework</groupId>
					<artifactId>spring-context</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>6.1.14</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot</artifactId>
			<version>3.2.4</version>
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-core</artifactId>
			<version>6.2.8</version>
			<exclusions>
				<exclusion>
					<groupId>org.springframework.security</groupId>
					<artifactId>spring-security-crypto</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>org.springframework.security</groupId>
			<artifactId>spring-security-crypto</artifactId>
			<version>6.3.8</version>
		</dependency>
		<dependency>
			<groupId>org.apache.httpcomponents</groupId>
			<artifactId>httpclient</artifactId>
			<version>4.5.14</version>
		</dependency>
		<dependency>
			<groupId>io.swagger.core.v3</groupId>
			<artifactId>swagger-models</artifactId>
			<version>2.1.2</version>
		</dependency>
		<dependency>
			<groupId>io.swagger.core.v3</groupId>
			<artifactId>swagger-annotations</artifactId>
			<version>2.1.2</version>
		</dependency>
		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-core</artifactId>
			<version>10.1.36</version>
		</dependency>
		<dependency>
			<groupId>org.apache.httpcomponents.core5</groupId>
			<artifactId>httpcore5</artifactId>
			<version>5.2</version>
		</dependency>
		<dependency>
			<groupId>jakarta.activation</groupId>
			<artifactId>jakarta.activation-api</artifactId>
			<version>2.1.2</version>
		</dependency>
		<dependency>
			<groupId>com.sun.activation</groupId>
			<artifactId>jakarta.activation</artifactId>
			<version>1.2.2</version>
		</dependency>
		<dependency>
			<groupId>com.github.ulisesbocchio</groupId>
			<artifactId>jasypt-spring-boot-starter</artifactId>
			<version>3.0.4</version>
		</dependency>
		<dependency>
			<groupId>org.apache.poi</groupId>
			<artifactId>poi-ooxml</artifactId>
			<version>5.2.3</version>
			<exclusions>
				<exclusion>
					<groupId>commons-io</groupId>
					<artifactId>commons-io</artifactId>
				</exclusion>
				<exclusion>
					<groupId>org.apache.commons</groupId>
					<artifactId>commons-compress</artifactId>
				</exclusion>
			</exclusions>
		</dependency>
		<dependency>
			<groupId>commons-io</groupId>
			<artifactId>commons-io</artifactId>
			<version>2.14.0</version>
		</dependency>
		<dependency>
			<groupId>org.apache.commons</groupId>
			<artifactId>commons-compress</artifactId>
			<version>1.26.0</version>
		</dependency>
	</dependencies>
	<build>
		<finalName>Report-It</finalName>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
			<plugin>
				<artifactId>maven-compiler-plugin</artifactId>
				<configuration>
					<forceJavacCompilerUse>true</forceJavacCompilerUse>
					<compilerArgs>
						<arg>-verbose</arg>
					</compilerArgs>
				</configuration>
			</plugin>
		</plugins>






org.springframework.context.ApplicationContextException: Unable to start web server
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:165) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:619) ~[spring-context-6.1.14.jar:6.1.14]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.refresh(ServletWebServerApplicationContext.java:146) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:754) [spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:456) [spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:334) [spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1354) [spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1343) [spring-boot-3.2.4.jar:3.2.4]
	at com.uhc.ei.reportit.ReportItApplication.main(ReportItApplication.java:22) [classes/:?]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[?:?]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77) ~[?:?]
	at jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[?:?]
	at java.lang.reflect.Method.invoke(Method.java:568) ~[?:?]
	at org.springframework.boot.devtools.restart.RestartLauncher.run(RestartLauncher.java:50) [spring-boot-devtools-3.2.5.jar:3.2.5]
Caused by: org.springframework.boot.web.server.WebServerException: Unable to start embedded Tomcat
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:145) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: org.apache.catalina.LifecycleException: A child container failed during start
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:768) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: java.util.concurrent.ExecutionException: org.apache.catalina.LifecycleException: A child container failed during start
	at java.util.concurrent.FutureTask.report(FutureTask.java:122) ~[?:?]
	at java.util.concurrent.FutureTask.get(FutureTask.java:191) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:756) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: org.apache.catalina.LifecycleException: A child container failed during start
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:768) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardHost.startInternal(StandardHost.java:772) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: java.util.concurrent.ExecutionException: org.apache.catalina.LifecycleException: java.lang.IllegalStateException: Unable to disable the global canonical file name cache or confirm that it is disabled when starting the WebResourceSet at [/Users/amish237/IdeaProjects/pioneers_pioneers-report-it/src/main/webapp] which is part of the web application [/Report-It]. The WebResourceSet may be exposed to CVE-2024-56337.
	at java.util.concurrent.FutureTask.report(FutureTask.java:122) ~[?:?]
	at java.util.concurrent.FutureTask.get(FutureTask.java:191) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:756) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardHost.startInternal(StandardHost.java:772) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: org.apache.catalina.LifecycleException: java.lang.IllegalStateException: Unable to disable the global canonical file name cache or confirm that it is disabled when starting the WebResourceSet at [/Users/amish237/IdeaProjects/pioneers_pioneers-report-it/src/main/webapp] which is part of the web application [/Report-It]. The WebResourceSet may be exposed to CVE-2024-56337.
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory$LoaderHidingWebResourceSet.initInternal(TomcatServletWebServerFactory.java:949) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.apache.catalina.util.LifecycleBase.init(LifecycleBase.java:122) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:155) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.webresources.StandardRoot.startInternal(StandardRoot.java:726) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardContext.resourcesStart(StandardContext.java:4162) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:4284) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardHost.startInternal(StandardHost.java:772) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more
Caused by: java.lang.IllegalStateException: Unable to disable the global canonical file name cache or confirm that it is disabled when starting the WebResourceSet at [/Users/amish237/IdeaProjects/pioneers_pioneers-report-it/src/main/webapp] which is part of the web application [/Report-It]. The WebResourceSet may be exposed to CVE-2024-56337.
	at org.apache.catalina.webresources.DirResourceSet.initInternal(DirResourceSet.java:364) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method) ~[?:?]
	at jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77) ~[?:?]
	at jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43) ~[?:?]
	at java.lang.reflect.Method.invoke(Method.java:568) ~[?:?]
	at org.springframework.util.ReflectionUtils.invokeMethod(ReflectionUtils.java:281) ~[spring-core-6.1.6.jar:6.1.6]
	at org.springframework.util.ReflectionUtils.invokeMethod(ReflectionUtils.java:265) ~[spring-core-6.1.6.jar:6.1.6]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory$LoaderHidingWebResourceSet.initInternal(TomcatServletWebServerFactory.java:946) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.apache.catalina.util.LifecycleBase.init(LifecycleBase.java:122) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:155) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.webresources.StandardRoot.startInternal(StandardRoot.java:726) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardContext.resourcesStart(StandardContext.java:4162) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:4284) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardHost.startInternal(StandardHost.java:772) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.ContainerBase$StartChild.call(ContainerBase.java:1193) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.FutureTask.run(FutureTask.java:264) ~[?:?]
	at org.apache.tomcat.util.threads.InlineExecutorService.execute(InlineExecutorService.java:75) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at java.util.concurrent.AbstractExecutorService.submit(AbstractExecutorService.java:145) ~[?:?]
	at org.apache.catalina.core.ContainerBase.startInternal(ContainerBase.java:749) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardEngine.startInternal(StandardEngine.java:203) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardService.startInternal(StandardService.java:415) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.core.StandardServer.startInternal(StandardServer.java:870) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:164) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.apache.catalina.startup.Tomcat.start(Tomcat.java:437) ~[tomcat-embed-core-10.1.36.jar:10.1.36]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.initialize(TomcatWebServer.java:126) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatWebServer.<init>(TomcatWebServer.java:105) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getTomcatWebServer(TomcatServletWebServerFactory.java:499) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.embedded.tomcat.TomcatServletWebServerFactory.getWebServer(TomcatServletWebServerFactory.java:218) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.createWebServer(ServletWebServerApplicationContext.java:188) ~[spring-boot-3.2.4.jar:3.2.4]
	at org.springframework.boot.web.servlet.context.ServletWebServerApplicationContext.onRefresh(ServletWebServerApplicationContext.java:162) ~[spring-boot-3.2.4.jar:3.2.4]
	... 13 more

	</build>

</project>
