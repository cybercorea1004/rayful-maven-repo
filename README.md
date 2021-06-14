# rayful-maven-repo
Rayful project repository

프로젝트 진행서 반복 또는 필수적인 사항들에 대한 공통 처리를 위한 모듈을 정의하고 사용합니다.

1. 기본(내부) 구성
   - springboot(2.4.5)
   - java(1.8)
   - spring cloud(2020.0.2)
   - spring admin(2.3.1)
   
   ex)설정 참조
   ```xml
   <parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.4.5</version>
		<relativePath /> <!-- lookup parent from repository -->
	</parent>
	<repositories>
		<repository>
			<id>jitpack.io</id>
			<url>https://jitpack.io</url>
		</repository>
	</repositories>
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.cloud</groupId>
				<artifactId>spring-cloud-dependencies</artifactId>
				<version>${spring-cloud.version}</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
			<dependency>
				<groupId>de.codecentric</groupId>
				<artifactId>spring-boot-admin-dependencies</artifactId>
				<version>${spring-boot-admin.version}</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>
	<!--Spring Cloud Finchley 사용함 -->
	<properties>
		<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
		<project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
		<java.version>1.8</java.version>
		<spring-cloud.version>2020.0.2</spring-cloud.version>
		<spring-boot-admin.version>2.3.1</spring-boot-admin.version>
	</properties>
   ```
2. 제공 component module
     - rcommon(공통모듈)
     - rscheduler(Sche module 탑재 스케쥴러 관리)
     - rsftp(sftp 사용)
     - rfcm(모바일 Push 모듈)
     - rrabbitmq(rabbitMQ)
     - rsocket(소켓 서버)
     - rdb(DB 설정)
     - remail(EMAIL 설정)
     - rredis(redis 설정 및 Pub/Sub)
     - rwebsocket(WebSocket 설정 Pub/Sub)
     
3. 사용 방법
 
   가. rcommon(공통모듈)
     - repository
     ```xml
<repository>
			<id>rayful-snapshot</id> <!-- 아무거나 적당히 -->
			<url>https://github.com/cybercorea1004/rayful-maven-repo/tree/master/snapshots</url> <!-- groupId/artifactId 위치 전 까지의 경로 -->
		</repository>
     ```
