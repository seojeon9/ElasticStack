# ElasticStack
### ElasticSearch, Kibana를 Docker-compose로 시작하기

1. Elasticsearch와 kibana가 통신할 네트워크 만들기
```
docker network elastic # 네트워크이름
docker network ls
```

2. Elasticsearch 이미지 가져오기
```
docker pull docker.elastic.co/elasticsearch/elasticsearch:7.14.1 # 원하는 버전
```

3. Kibana 이미지 가져오기
```
docker pull docker.elastic.co/kibana/kibana:7.14.1 # 버전 맞춰주기
```

4. Docker-compose.yml 파일 원하는 위치에 작성해주기
    - image : 사용할 이미지 이름 및 버전
    - container_name : 지정할 컨테이너 이름
    - networks : 네트워크 이름
    - ports : 사용할 포트 (공식문서 참조)
    - links : kibana를 elasticsearch와 연결해줘야함
    - volumes : 본인이 원하는 볼륨 방식 및 위치로 설정

    
5. Docker-compose 실행하기
```
pip3 install docker-compose
docker-compose up -d # 백그라운드로 실행하기
docker-compose down
```
   
참조 : https://www.elastic.co/guide/en/elasticsearch/reference/7.14/docker.html
