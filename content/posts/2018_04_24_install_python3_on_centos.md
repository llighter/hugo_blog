---
title: "CentOS7 에 Python 3.6.x 설치하기"
date: 2018-04-24T20:59:51+09:00
draft: false
---

{{< youtube kjGBe55Js78 >}}

> 이 글은 **Jani Karhunen**이 쓴 [How-to install Python 3.6.1 on CentOS 7][1] 포스트를 발쵀 및 번역한 글입니다.

CentOS 7에는 Python 2.7이 기본적으로 제공된다. 물론 Python 2.7으로도 많을 것을 할 수 있지만 Python 3이 제공하는 다양한 기능을 사용하고 싶은 경우에는 설치를 해야한다.

# 준비사항

- 구동가능한 CentOS 7 서버
- Sudo 권한을 가진 계정

> 이 글에서는 Google Cloud Platform의 Compute Engine을 사용해서 서버를 구성할 것이다.

# 필수 유틸리티 설치

리눅스 환경에서 작업을 하다보면 압축을 풀거나 파일을 다운받는 등 기본적인 기능을 사용하기 위한 유틸리티가 필요하다. **yum** 패키지 매니저를 사용해서 필수적인 유틸리티들을 한번에 설치하겠다.

{{< highlight bash >}}
sudo yum update
sudo yum install yum-utils
sudo yum groupinstall development
{{< / highlight >}}

이제 필수적인 패키지들이 설치가 완료되었다.

# Python 3.6.x 설치하기

기본적인 **yum** 저장소는 아직 최신의 파이썬 버전을 제공하고 있지 않기 때문에 필수적인 RPM 패키지를 제공해주는 **IUM**(Inline with Upstream Stable) 이라 불리는 저장소를 추가적으로 설치해줘야한다.

그럼 IUM 저장소를 설치하자.

{{< highlight bash >}}
sudo yum install https://centos7.iuscommunity.org/ius-release.rpm
{{< / highlight >}}

이제 저장소를 설치했으니 Python 3.6을 설치해보자

{{< highlight bash >}}
sudo yum install python36u
{{< / highlight >}}

이제 설치된 파이썬 버전을 확인해보자.(이 글이 작성된 시점에서 설치된 버전은 **Python 3.6.4**이다.)

{{< highlight bash >}}
python3.6 -V
{{< / highlight >}}

다음으로는 파이썬 패키지를 관리할 수 있는 **pip**과 개발 패지키들을 설치해보자
{{< highlight bash >}}
sudo yum install python36u-pip
sudo yum install python36u-devel
{{< / highlight >}}

설치된 버전을 최종적으로 확인해보자.
{{< highlight bash >}}
# 여기에는 시스템에 설치된 파이썬 버전이 나타나야 한다
python –V
# 결과:
Python 2.7.5

# 여기에는 파이선3의 버전이 나타나야 한다
python3.6 –V
# 결과:
Python 3.6.4
{{< / highlight >}}

이걸로 Python3.6 버전을 설치하는 과정을 살펴보았다.

# 가상환경(virtualenv) 만들기

프로젝트별로 상이한 의존성을 가진 패키지를 관리하는 것은 매우 힘든일이다.
그래서 프로젝트 별로 가상의 환경을 구성해서 사용할수 있는 방법에 대해 알아보자.

Python3에서 virtualenv를 생성하는 주된 방식을 알아보자.

{{< highlight bash >}}
python3.6 -m venv venv
{{< / highlight >}}

앞에 쓴 **venv**는 가상환경(virtualenv)를 생성하는 명령어이고 뒤에 **venv**는 생성할 가상환경의 이름이다.
이제 생성된 가상환경을 활성화하고 이 환경에서 패키지들을 관리 할 수있다.

{{< highlight bash >}}
. venv/bin/activate
pip install [package_name]
pip install -r requirements.txt
{{< / highlight >}}

[1]: https://janikarhunen.fi/how-to-install-python-3-6-1-on-centos-7.html