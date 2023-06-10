#MYSQL 도커파일 생성 방법

```
FROM mysql

ENV MYSQL_USER=jms
ENV MYSQL_PASSWORD=jms0501
ENV MYSQL_ROOT_PASSWORD=root1234
ENV MYSQL_DATABASE=jmsdb

CMD ["--character-set-server=utf8mb4", "--collation-server=utf8mb4_unicode_ci"]
```

## UTF  8 설정 확인 방법
```
show variables like 'character_set_%'
```

## 볼륨 옵션으로 호스트 폴더 연결해서 실행하는 방법
```
docker run -d -v c:/workspace/docker/meta-coding/ex05/mysql-volume:/var/lib/mysql -p 3307:3006 --name mysql-container mysql-image
```

## 이름이 있는 볼륨 사용법
```
docker run -d -v mysql-volume:/var/lib/mysql -p 3307:3306 --name mysql-container mysql-image
```