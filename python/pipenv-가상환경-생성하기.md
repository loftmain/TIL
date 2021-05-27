# Pipenv 가상 환경 생성하기

---
## 가상 환경 구성
패키지 관리를 하고싶은 프로젝트 폴더로 이동

가상 환경에서 사용할 파이썬 버전을 `--python` 옵션을 명시하여 
`pipenv`커맨드를 실행하면 가상환경이 만들어집니다.

`pipenv --python 3.8`

생성되는 `Pipefile`은 프로젝트의 메타 정보가 저장됩니다.

가상 환경과 파이썬 인터프리터의 위치를 보는 커맨드 입니다.

```
$ pipenv --venv
/home/ubuntu/.local/share/virtualenvs/project_folder-Ntmpf5cn
$ pipenv --py
/home/ubuntu/.local/share/virtualenvs/project_folder-Ntmpf5cn/bin/python
```

## 파이썬 실행

`pipenv run` 커맨드를 이용

```angular2html
$ pipenv run python
Python 3.8.10 (default, May  5 2021, 03:01:07)
[GCC 7.5.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import sys
>>> sys.executable
'/home/ubuntu/.local/share/virtualenvs/project_folder-Ntmpf5cn/bin/python'
```

## 가상 환경 사용

`pipenv shell` 커맨드를 사용해서 `venv`나 `virtualenv`처럼 터미널에서 가상 환경을 활성화할 수 있습니다.

```angular2html
$ pipenv shell
Launching subshell in virtual environment...
. /home/ubuntu/.local/share/virtualenvs/project_folder-Ntmpf5cn/bin/activate

$ which python
/home/ubuntu/.local/share/virtualenvs/project_folder-Ntmpf5cn/bin/python
```

```
(project_folder) ubuntu:~/project_folder$ exit
exit
ubuntu:~/project_folder$ which python
/usr/bin/python
```


가상 환경 제거는 `pipenv --rm` 커맨드를 실행하면 됩니다.

## 패키지 설치

`requests` 패키지를 설치해보겠습니다.

```angular2html
$ pipenv install requests
Installing requests...
Adding requests to Pipfile's [packages]...
✔ Installation Succeeded
Pipfile.lock not found, creating...
Locking [dev-packages] dependencies...
Locking [packages] dependencies...
Building requirements...
Resolving dependencies...
✔ Success!
Updated Pipfile.lock (fbd99e)!
Installing dependencies from Pipfile.lock (fbd99e)...
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
```

- Pipenv
```angular2html
[packages]
requests = "*"
```

`Pipefile.lock` 파일도 생성되어 있는 것을 볼 수 있습니다. 이 파일은 설치된 패치키의 버전과
그 패키지가 의존하는 다른 패키지들의 정확한 버전을 기억하기 위해서 자체적으로 사용하는 파일입니다.
따라서 `pipenv`는 `Pipenv.lock` 이라는 패키지 잠금 파일을 이용해서 `Pipefile`파일에 정확한
버전이 명시되어 있지 않더라도 항상 동일한 버전의 패키지를 설치할 수 있도록 해줍니다.

## 개발용 패키지 설치

애플리케이션 실행에 필요한 일반 패키지와 개발에만 필요한
패키지를 `--dev` 옵션을 줘서 설치할 수 있습니다.

```angular2html
$ pipenv install pytest --dev
```

## 모든 패키지 한 번에 설치

```angular2html
$ pipenv install

$ pipenv install --dev
```