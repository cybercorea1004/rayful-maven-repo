# rayful-maven-repo
Rayful project repository

프로젝트 진행서 반복 또는 필수적인 사항들에 대한 공통 처리를 위한 모듈을 정의하고 사용합니다.

1. 기본(내부) 구성
   - springboot(2.4.5)
   - java(1.8)
   - spring cloud(2020.0.2)
   - spring admin(2.3.1)
   
   ex) parent module 설정
   
   ---------------------------------------------------
   
  
  ---------------------------------------------------

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
   
