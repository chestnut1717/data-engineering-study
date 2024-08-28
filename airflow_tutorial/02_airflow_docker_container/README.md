1. Docker 설치

2. 공식 문서에 들어가
  - https://airflow.apache.org/docs/apache-airflow/stable/howto/docker-compose/index.html
  - MAC, Linux: ```curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.10.0/docker-compose.yaml'``` 
  - Windows: ```Invoke-WebRequest -Uri 'https://airflow.apache.org/docs/apache-airflow/2.10.0/docker-compose.yaml' -OutFile 'docker-compose.yaml'```

3. yaml파일 수정
  -     AIRFLOW__CORE__EXECUTOR: CeleryExecutor 에서 LocalExecutor로 변경
  - CeleryExecutor를 사용하지 않으므로 redis관련 dependency, definitinon 제거파일 참고

4. 필요한 디렉토리 생성
- MAC, Windows에서는 echo 안해도 된다
```
mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env
```
- Windows
```
New-Item -ItemType Directory -Force -Path .\dags, .\logs, .\plugins, .\config

```

5. Database init
- airflow에 필요한 이미지 다운로드 자동으로 함

```
docker compose up airflow-init
```

6. Airflow RUN 
Airflow 실행시키기

```
docker compose up
```