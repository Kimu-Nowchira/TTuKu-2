# TTuKu
> 놀자로 글자! 트꾸 온라인

**트꾸**는 여러분이 태어나서 들어본 적도 없는 9글자 이상의 괴상한 단어들을 외워야 즐길 수 있는 고인물 게임입니다.
로봇과 혼자서 게임을 할 수도 있고, 서버에 접속해 있는 다른 사람들과 함께 할 수도 있지만, 트꾸 서버에 같이 할 다른 사람은 없을 겁니다.
이 저장소는 여러분이 **트꾸**를 즐기기 위해 준비해야 할 것들에 대해 딱히 알리고 있지 않습니다.

---
### 목표
**트꾸**는 2014년 개발된 [**끄투**](https://github.com/JJoriping/KKuTu)를 ES2022 기반의 타입스크립트로 리노베이션하여 새로운 게임을 만드는 것을 목표로 하는 프로젝트입니다.

이 프로젝트의 프로세스는 다음과 같습니다.
1. non-strict한 TypeScript로 게임 서버와 웹서버를 재구성
  - ES2016 기반의 문법 사용
  - no-semi 스타일 적용
  - ES2016 이상의 문법 사용
  - 클래스 역할을 하는 모든 메서드를 클래스로 교체
  - 구조를 직관적으로 개선
  
1. ES2022 기반의 strict한 TypeScript로 게임 및 웹 서버를 완성


### 설치 방법
#### Windows 환경
1. 윈도우 따위

#### Linux 환경
1. 이 레포지토리를 클론합니다. (`git clone https://github.com/Kimu-Nowchira/TTuKu-2.git`)
1. Docker를 설치합니다. 이미 설치된 경우 다음 단계로 넘어갑니다.
1. 레포지토리 폴더 내에서 `sudo docker-compose up -d --build`를 실행합니다.

#### 공통
- `global.example.json`과 `auth.example.json`을 같은 경로에 복사하여 oAuth 설정 파일(`auth.json`)과 전역 설정 파일(`global.json`)을 **반드시** 만들어 주세요.
  - 도커 기본 설정을 사용할 경우 추가로 설정을 변경하지 않아도 정상 작동하지만 보안을 위해 비밀번호, 토큰 등을 변경해 주세요.
  - 도커를 사용하며 PostgreSQL 서버 비밀번호를 변경할 경우 `docker-compose.yml`의 `POSTGRES_PASSWORD`를 변경해 주세요.
- 본 레포지토리에는 [WordNet](https://wordnet.princeton.edu/) 자료가 포함되어 있습니다. 서버를 운영할 때 반드시 사용자에게 이에 대한 라이선스를 안내해야 합니다.
- 서버가 정상적으로 설치된 다음부터는 서버를 실행시키기 위해서 가장 마지막 단계만 수행하면 됩니다.
- 서버가 성공적으로 열린 후 웹 브라우저에서 `127.0.0.1:2930`(다른 사람들은 해당 컴퓨터의 외부 IP 주소:2930)로 접속하여 끄투를 즐길 수 있습니다.
  - 외부 포트는 global.json이 아닌 docker-compose.yml에서 변경해야 합니다. 기본 외부 포트는 2930입니다.
- Docker에 Postgres, Redis 등에 관한 모든 기본 설정이 되어 있습니다. Docker를 사용하신다면 따로 DB를 세팅하실 필요가 없습니다.
- [Cloudflare](https://www.cloudflare.com/)를 이용하는 경우, DNS 탭의 status를 `DNS only`로 두세요. `DNS and HTTP proxy (CDN)`으로 둘 경우, 방 만들기와 방 입장이 불가합니다.

### 라이선스
- 끄투 원 레포지토리 기반의 소스 코드에 대해: [GNU 일반 공중 사용 라이선스](https://github.com/JJoriping/KKuTu/blob/master/LICENSE)
- 모든 이미지 및 소리에 대해: [크리에이티브 커먼즈 라이선스 CC BY](https://creativecommons.org/licenses/by/4.0/)
	- 다만 본 레포지토리에서 제공하는 소스 코드로 끄투 서비스를 운영하기 위해 이들을 사용하는 경우 저작자 표시(BY)를 생략할 수 있습니다.
