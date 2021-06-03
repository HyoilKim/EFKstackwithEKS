## AWS EKS 를 사용하여 Nginx 및 EFK 스택 구축

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
