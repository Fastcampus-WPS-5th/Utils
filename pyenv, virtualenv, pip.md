# pyenv, virtualenv, pip

## pyenv

프로젝트별로 파이썬 버전을 따로 관리할 수 있도록 도와주는 라이브러리.  

여러 프로젝트를 동시에 진행하다보면, 어떤 프로젝트에서는 2.7을, 어떤 프로젝트에서는 3.5를 사용하는 식으로 다양한 버전을 사용할 수 있기 때문에 `pyenv`를 사용해서 파이썬 버전을 관리한다.

## virtualenv, pyenv-virtualenv
  
프로젝트별로 설치된 패키지들 간 충돌을 막아주기 위해 분리된 파이썬 환경을 만들어주는 `virtualenv`라는 패키지를 사용하며, `pyenv`를 사용할 경우, 가상환경을 `pyenv`와 좀 더 밀접하게 사용 할 수 있도록 나온 `pyenv-virtualenv`패키지를 사용한다.

---

### pyenv install

#### 패키지 설치

**macOS**  
 
```
brew install pyenv
brew install pyenv-virtualenv
```

**Ubuntu**

<https://github.com/yyuu/pyenv-installer>  

```
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
```

#### 설치 후 pyenv관련 설정을 shell설정에 추가  

**macOS**  

```
vi ~/.bash_profile

# 가장 아래쪽에 아래 문장 추가
export PYENV_ROOT=/usr/local/var/pyenv
if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi
```

**Ubuntu**  

```
vi ~/.bashrc

# 가장 아래쪽에 아래 문장 추가
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```

#### shell설정을 바꾼 이후, 해당 설정을 현재 shell에 적용

터미널을 재시작하거나 `source ~/.bashrc` 또는 `source ~/.bash_profile`을 실행

#### pyenv를 이용해 파이썬을 설치 하기 전, 필요 패키지 설치

<https://github.com/yyuu/pyenv/wiki/Common-build-problems>

#### 설치 가능한 파이썬 버전 보기

```
pyenv install --list
```

#### 파이썬 3.5.3설치

```
pyenv install 3.5.3
```

---

### pyenv-virtualenv를 사용한 가상환경 관리

#### 컴퓨터 전체에서 사용할 파이썬 환경 설정

```
pyenv global <version or env_name>
```

#### 가상환경 생성

```
pyenv virtualenv <version> <env_name>
```

#### 가상환경을 해당 폴더에서 사용하도록 지정

```
pyenv local <env_name>
```

#### 현재 가상환경이 적용되어있는지 확인

```
pyenv version
```

---

## pip (Pip Installs Packages)

파이썬 패키지 관리자. 파이썬 패키지를 쉽게 설치하고 관리해준다.

### 관련 명령어

```
pip list
pip uninstall
pip install
```

### requirements가 있을 경우 설치

```
pip install -r requirements.txt
```

### 에러 해결

#### ImportError: No module named 'packaging'

```
pip install --upgrade pip
```
실행 후 다시 `pip install`

#### Could not import setuptools which is required to install from a source distribution.

```
pip install -U setuptools
```
실행 후 다시 `pip install`
