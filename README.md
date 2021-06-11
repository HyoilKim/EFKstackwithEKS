## EKS 를 사용한 EFK stack 구축 및 Slack 알림 전송

### 1. VPC 구성 [(상세링크)](https://www.notion.so/VPC-Bastion-Host-OS-b9f159effd9e4fe39e045ac74755a4c0)
- 서버 아키텍처<br>
  ![image](https://user-images.githubusercontent.com/23691938/120652844-1ed2ec00-c4bb-11eb-8c63-17eb843894fb.png)
- Subnet 이중화 구성
- Public Subnet과 IGW 연결
- 라우팅 테이블 설정
- Bastion Host 역할로서 NAT instance 생성(free)

### 2. Nginx 배포[(상세링크)](https://www.notion.so/EKS-5dbdb21db4f5460f93e9f9ada245b5e7)
- EKS Cluster 생성
- nginx.yaml 파일 생성하여 배포


### 3. EFK 배포[(상세링크)](https://www.notion.so/EKS-5dbdb21db4f5460f93e9f9ada245b5e7)
- elasticsearch/kibana.yaml 파일 생성하여 배포
  - loadbalancer listener 설정
  - loadbalancer inbound port 설정
- fluentd.yaml 파일 생성하여 배포

### 4. Slack 알림 전송
- CloudWatch에서 알람 발생 → SNS 푸시 서비스 호출 → Lambda 함수 트리거 → 연동된 Slack 채널로 알람 전송 <br>
  ![image](https://user-images.githubusercontent.com/23691938/121677006-485dca00-caf0-11eb-9ede-98277ccf7c1c.png)
  
- 결과
  ![cpu-alarm](https://user-images.githubusercontent.com/23691938/121678000-94f5d500-caf1-11eb-954b-58ef405a5992.JPG)
  ![slack-alarm](https://user-images.githubusercontent.com/23691938/121678009-97f0c580-caf1-11eb-97a0-e81fb9d561d4.JPG)
