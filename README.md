# django-tutorial

> #### 학습목표
>
> 장고의 기본적인 내용을 알아 본다.



#### 환경설정

- 파이썬 설치 확인

  ```bash
  $> python --verson
  Python 3.6.4
  ```

- 장고 설치

  > python 3버전 이상은 pip이 자동으로 설치되어 있으므로 pip을 이용해
  > django 를 설치한다.

  ```bash
  $> pip install Django
  $> python -m django --version
  2.2.2
  ```



#### 프로젝트 생성

- mysite라는 프로젝트를 생성

  ```bash
  $> django-admin startproject mysite
  ```



- 상위 mysite이름 변경

  > mysite 프로젝트를 생성하면 **mysite** 디렉토리와 **mysite** 디렉토리 하부에
  > **mysite** 폴더가 생성되는데 하위 디렉토리는 **프로젝트 디렉토리**이고 상위 디렉토리
  > 는 **프로젝트 관련 디렉토리/파일을 모으는 역할을 하는 디렉토리** 이다
  >
  > 같은 이름이라 헷갈 릴수 있으므로 상위 mysite 이름을 ch3로 변경한다.

  ```bash
  $> mv mysite ch3
  ```

  

- polls라는 애플리케이션을 생성

  ```bash
  $> cd ch3
  $> python manage.py startapp polls
  ```

  

