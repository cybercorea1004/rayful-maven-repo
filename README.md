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
     - rdb(DB 설정)
     - rscheduler(Sche module 탑재 스케쥴러 관리)
     - rsftp(sftp 사용)
     - rfcm(모바일 Push 모듈)
     - rrabbitmq(rabbitMQ)
     - rsocket(소켓 서버)     
     - remail(EMAIL 설정)
     - rredis(redis 설정 및 Pub/Sub)
     - rwebsocket(WebSocket 설정 Pub/Sub)
     
3. 사용 방법
 
   가. rcommon(공통모듈)
     - repository
     ```xml
	<repository>
	<id>rayful-snapshot</id> <!-- 아무거나 적당히 -->
	<url>https://github.com/cybercorea1004/rayful-maven-repo/tree/master/snapshots</url>
	</repository>
     ```
     - yml 설정
     ```
	pdf: 
	  target: 
	    server: 
	      path: 파일 디렉토리 패스
	logging:
	  file: 
	    path: ./
	    name: ./applicationRun.log
	  pattern:
	    file: -%clr(%d{yyyy-MM-dd HH:mm:ss.SSS}){faint} %clr(%5p) %clr(${PID}){magenta} %clr(---){faint} %clr([%15.15t]){faint} %clr(%-40.40logger{39}){cyan} %clr(:){faint} %m%n%wEx
     ```
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rcommon</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   나. rdb(DB 설정 / common에 포함)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rdb</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   다. rscheduler(Sche module 탑재 스케쥴러 관리)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rscheduler</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   라. rsftp(sftp 사용)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rsftp</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   마. rfcm(모바일 Push 모듈)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rfcm</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   바. rrabbitmq(rabbitMQ)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rrabbitmq</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   사. rsocket(소켓 서버)   
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rsocket</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   아. remail(EMAIL 설정)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>remail</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   자. rredis(redis 설정 및 Pub/Sub)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rredis</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
   차. rwebsocket(WebSocket 설정 Pub/Sub)
     - dependency
     ```xml
	<dependency>
		<groupId>kr.co.rayful</groupId>
		<artifactId>rwebsocket</artifactId>
		<version>0.0.1</version>
	</dependency>
     ```
