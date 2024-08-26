# Airflow Practice
- 참고 강의 : https://www.youtube.com/watch?v=K9AnJ9_ZAXE&t=2s

1. 가상환경 생성
  - python3 -m venv py_env
  - python verson == 3.12.2

2. 설치(https://github.com/apache/airflow)
  - ```pip install 'apache-airflow==2.10.0' --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.10.0/constraints-3.8.txt"```

3. airflow 환경변수 설정
- 절대경로로 써야 airflow.exceptions.AirflowConfigException이 뜨지 않는다.
- ```export AIRFLOW_HOME=/Users/park/study/data_engineering/airflow_tutorial/```

4. db 초기화
- ```airflow db init```

5. airflow webserver 열기(포트 설정 가능)
- ```airflow webserver -p 8080```

6. airflow user 생성하기
- ```airflow users create --username admin --firstname root --lastname root --role Admin --email admin@domain.com```
