# Geodjango - dev

 Django 공식 문서에 있는 geodjango 프로젝트의 docker 이미지 및 docker-compose 파일



- django
  - Django==2.1.5
  - Pillow=5.4.1
  - psycopg2==2.7.7
- postgresql
  - docker hub의 이미지 사용
  - 소스 링크 : https://github.com/appropriate/docker-postgis/tree/f6d28e4a1871b1f72e1c893ff103f10b6d7cb6e1/10-2.4



## COMMAND

- 도커 컴포즈 실행

````cmd
docker-compose up -d
````

- 데이터 베이스(postgresql) 데이터는 docker volume에 저장되도록 설정

  - 처음 컴포즈 파일을 돌릴 때는 데이터 베이스 설정을 해주어야 함
  - geodjango 컨테이너에 접속

  ```cmd
  docker exec -it <geodjango container id> bash
  ```

  - Django 슈퍼 유저 생성

  ```bash
  python manage.py createsuperuser
  ```

  - django shell에 접속 후 데이터 생성

  ```bash
  python manage.py shell
  ```

  ```python
  >>> from world import load
  >>> load.run()
  ```

  

