# django-tutorial

> #### 학습목표
>
> 장고의 기본적인 내용을 알아 본다.
> 여기 설명은 모두 파이썬 웹 프로그래밍 도서를 참조하고
> 거기에 대한 설명을 그대로 차용해서 작성했습니다.



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



#### 프로젝트 설정 변경

> mysite 디렉토리에 settings.py를 열어 프로젝트 설정을 변경한다.

- ALLOW_HOSTS에 허용할 host만 추가

  > **Django** *DEBUG=True* 이면 개발 모드 *False* 이면 운영 모드로 인식
  >
  > 운영 모드의 경우에는 *ALLOWD_HOSTST* 에 반드시 서버의 IP나 도메인을
  >
  > 지정해야 한다.
  >
  > 개발 모드의 경우에는 값을 지정하지 않아도 **['localhost', '127.0.0.1']** 로 간주



- ***polls*** 어플리케이션을 설정파일에 등록

  > 프로젝트에 포함되는 애플리케이션들은 모두 설정 파일에 등록해야 한다.
  > 여기서 생성한 ***polls*** 어플리케이션도 등록 해야한다.
  >
  > 애팔리케이션의 모듈명인 'polls' 만 등록해도 되지만, 애플리케이션의 설정 클래스로 등록하는게 더 정확한 방법

  ```python
  INSTALLED_APPS = [
  	....,
    'polls.apps.PollsConfig', #추가
  ]
  ```



- 타임존 지정

  > 최초에는 세계 표준시(UTC)로 되어 있는데, 한국 시간으로 변경

  ```python
  TIME_ZONE = 'Asia/Seoul'
  ```



#### 기본 테이블 생성

> 장고는 모든 웹 프로젝트 개발 시 반드시 사용자와 그룹 테이블이 필요하다는 가정하에
> 설계. 그래서 테이블을 전혀 만들지 않더라도 사용자 및 그룹 테이블을 만들어 주기 위해서 프로젝트 개발 시작 시점에 이 명령어를 실행



```bash
$> python manage.py migrate
Operations to perform:
  Apply all migrations: admin, auth, contenttypes, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying auth.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying auth.0010_alter_group_name_max_length... OK
  Applying auth.0011_update_proxy_permissions... OK
  Applying sessions.0001_initial... OK

```



#### 서버 구동

``` bash
$> python manage.py runserver
```

[127.0.0.1:8000](127.0.0.1:8000) 번으로 접속