![MagicMirror²: 모듈화 가능한 오픈 소스 스마트 미러 플랫폼. ](.github/header.png)

<p align="center">
	<a href="https://david-dm.org/MichMich/MagicMirror"><img src="https://david-dm.org/MichMich/MagicMirror.svg" alt="Dependency Status"></a>
	<a href="https://david-dm.org/MichMich/MagicMirror#info=devDependencies"><img src="https://david-dm.org/MichMich/MagicMirror/dev-status.svg" alt="devDependency Status"></a>
	<a href="https://bestpractices.coreinfrastructure.org/projects/347"><img src="https://bestpractices.coreinfrastructure.org/projects/347/badge"></a>
	<a href="http://choosealicense.com/licenses/mit"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
	<a href="https://travis-ci.org/MichMich/MagicMirror"><img src="https://travis-ci.org/MichMich/MagicMirror.svg" alt="Travis"></a>
	<a href="https://snyk.io/test/github/MichMich/MagicMirror"><img src="https://snyk.io/test/github/MichMich/MagicMirror/badge.svg" alt="Known Vulnerabilities" data-canonical-src="https://snyk.io/test/github/MichMich/MagicMirror" style="max-width:100%;"></a>
</p>

**MagicMirror²** 는 모듈화 가능한 오픈 소스 스마트 미러 플랫폼입니다. 많은 모듈을 추가함에 따라 **MagicMirror²**는 복도와 화장실 등, 어느 곳에서 당신만의 개인비서가 될 수 있습니다.
**MagicMirror²**는 [초기 버전의 MagicMirror](http://michaelteeuw.nl/tagged/magicmirror)제작자와 [커뮤니티 기여자들](https://github.com/MichMich/MagicMirror/graphs/contributors)의 도움속에서 제작되었습니다.

MagicMirror²는 모듈화되어있는 플러그인 시스템과 어플리케이션 wrapper인 [Electron](http://electron.atom.io/)의 사용에 초점이 맞추어져 있는 스마트 미러 플랫폼입니다. 따라서, 추가적인 웹 서버나 브라우저의 설치가 필요하지 않습니다!

## Magic Mirror 한글 메뉴얼에 대하여

대한민국 성남시에 위치한 가천대학교 소프트웨어학과에 재학중인 양유성 학생(Fallingstar)이 작성하고, 모든 커뮤니티 기여자들과 함께 수정 중인 한글 버전의 Magic Mirror repository입니다.
원본 repository의 주소는 [이 곳](https://github.com/MichMich/MagicMirror)에서 확인하실 수 있습니다.
모두가 pull request를 보내실 수 있습니다만, 효율적인 작업을 위해, [기여 가이드라인](#기여-가이드라인)을 참조해주시길 바랍니다.

## 개요

- [사용법](#사용법)
- [설정 방법](#설정-방법)
- [모듈](#모듈)
- [커뮤니티](#커뮤니티)
- [기여 가이드라인](#기여-가이드라인)

## 사용법

### 라즈베리 파이 지원
MagicMirror²에 사용된 어플리케이션 wrapper인 Electron은 라즈베리 파이 2 & 3 시리즈만을 지원합니다. 즉, 라즈베리 파이 1시리즈는 현재 지원되지 **않습니다**. 만약 라즈베리 파이 1에서의 구동을 원하신다면, 전체 화면 브라우저에서의 [서버 구동](#서버-구동)기능을 참조하여 주시길 바랍니다.

### 자동 설치 방법 (오직 라즈베리 파이에서만 지원됩니다!)

MagicMirror²를 설치할 라즈베리 파이에서 다음 명령어를 실행합니다:
````
bash -c "$(curl -sL https://raw.githubusercontent.com/MichMich/MagicMirror/master/installers/raspberry.sh)"
````

### 수동 설치 방법

1. 최신 버전의 Node.js를 다운로드한 뒤, 설치합니다.
2. 해당 repository를 clone하고 beta branch를 check out합니다: `git clone https://github.com/MichMich/MagicMirror`
3. MagicMirror²를 설치한 폴더로 이동합니다: `cd ~/MagicMirror`
4. MagicMirror²를 설치하고 실행합니다: `npm install && npm start`

**주의점:** `npm start` 명령어는 SSH를 통해 사용할 수 **없습니다**. 대신, `DISPLAY=:0 nohup npm start &`를 사용하시길 바랍니다. 해당 명령어를 통해, 원격으로 어플리케이션을 실행할 수 있을 것입니다.

**알림:** 라즈베리 파이에서 debug를 하고 싶으시다면, `npm start dev` 명령어를 통해 MagicMirror 어플리케이션을 개발자 도구와 함께 실행시키시길 바랍니다.

### 서버 구동

특정 상황에서, 어플리케이션을 app window없이 실행시키고 싶을 때, 사용할 수 있는 방법입니다. MagicMirror가 설치된 폴더에서 다음 명령어를 입력하세요:`node serveronly` 이를 통해, 서버 모드의 MagicMirror가 실행 되었을 것이며, 설치한 브라우저를 통해 MagicMirror의 화면을 띄울 수 있을 것입니다.

### 라즈베리 파이의 설정과 자동 실행

다음 링크들은 여러분의 MagicMirror²를 실행시킬 때 필요한 유용한 설정법을 포함하고 있습니다:

- [라즈베리파이 기본 설정](https://github.com/stardung86/MagicMirror/wiki/라즈베리파이-기본-설정)
- [MagicMirror 자동 실행](https://github.com/stardung86/MagicMirror/wiki/MagicMirror-자동-실행)

### MagicMirror² 업데이트 하기

만약 여러분이 자신의 MagicMirror²를 최신 버전으로 업데이트하고 싶으시다면, 터미널을 이용해서, MagicMirror 폴더로 이동한 뒤, 다음 명령어를 실행하시길 바랍니다:
```bash
git pull && npm install
```

config와 modules외의 다른 것을 수정하지 않았다면, 문제 없이 실행될 것입니다.
`git status`를 입력함으로써 여러분의 수정 내역을 확인할 수 있습니다. 만약 여러분의 MagicMirror를 초기화하고 싶다면, `git reset --hard`를 입력하시길 바랍니다. 그 후, 정상적으로 git pull을 시도할 수 있을 것입니다.

## 설정 방법

1. `config/config.js.sample`파일을 `config/config.js`와 같이 복제합니다.
2. 필요한 값을 설정합니다.

수정 가능한 설정 값은 다음과 같습니다:

| **설정 값** | **설명** |
| --- | --- |
| `port` | MagicMirror²의 서버가 실행될 port입니다. 기본 값은 `8080`입니다. |
| `address` | MagicMirror²의 서버가 실행될 IP주소입니다. 기본적으로 설정 되어있는 값은 IPv6를 대상으로 한 `::`와 IPv4를 대상으로 한 `0.0.0.0`입니다. 예시: `192.168.10.100` |
| `ipWhitelist` | MagicMirror²로 접속할 수 있는, 허가 받은 IP주소입니다. 기본 값은 `["127.0.0.1", "::ffff:127.0.0.1", "::1"]`입니다. 서브넷 마스크(`["127.0.0.1", "127.0.0.1/24"]`) 혹은 IP 범위(`["127.0.0.1", ["192.168.0.1", "192.168.0.100"]]`)를 활용할 수도 있습니다. |
| `zoom` | 어플리케이션의 내용이 얼마나 확대되어 보일지에 대한 설정 값입니다. 기본 값은 `1.0`입니다. |
| `language` | 어플리케이션이 사용할 언어입니다. (알림: 모든 언어가 번역되어있지는 않습니다.) 가능한 언어는 languages 폴더를 확인해주시길 바랍니다. 기본 설정 언어는 영어(`en`)입니다. |
| `timeFormat` | 시간을 표시할 때 사용하기 위한 표현법입니다. `12시간` 표현법 과 `24시간` 표현법이 존재합니다. 기본 값은 `24` 입니다. |
| `units` | 기본 날씨 모듈에서 사용할 단위 표시법입니다. 가능한 설정으로는 미터법(`metric`)과 야드법(`imperial`)이 있습니다. 기본 설정은 미터법(`metric`)입니다. |
| `modules` | 활성화된 모듈의 목록입니다. **각 모듈은 모듈만의 설정 값을 가질 수 있습니다. 다음 테이블을 참조하시길 바랍니다.** |
| `electronOptions` | Electron(브라우저) 옵션의 목록입니다. 브라우저 크기(defaults `.width = 800` & `.height = 600`)와 같은 보편적인 값을 설정할 수 있습니다. `.kiosk = true`, `.autoHideMenuBar = false`, `.fullscreen = false`와 같이 설정함으로써 Kiosk mode를 활성화할 수 있습니다. 더 많은 옵션은 [이 곳](https://github.com/electron/electron/blob/master/docs/api/browser-window.md)을 참조하시길 바랍니다. |


모듈 설정 값:

| **설정 값** | **설명** |
| --- | --- |
| `module` | 모듈의 이름입니다. 또한, 모듈이 저장되어있는 폴더에 대한 내용도 작성할 수 있습니다. 가능한 예시로는 `clock`, `default/calendar`, `custommodules/mymodule`와 같은 것이 있습니다. |
| `position` | 모듈이 실행될 위치입니다. 가능한 값으로는 `top_ bar`, `top_left`, `top_center`, `top_right`, `upper_third`, `middle_center`, `lower_third`, `bottom_left`, `bottom_center`, `bottom_right`, `bottom_bar`, `fullscreen_above`, `fullscreen_below`와 같은 것이 있습니다. 이 설정 값은 필수가 아니지만, 대부분의 모듈에서 작성하시길 권장합니다. 각 모듈의 문서를 참조하여 더 많은 정보를 얻으세요. 또한, 많은 모듈이 같은 위치 값으로 설정되어있다면, 설정 파일에 적혀있는 순서를 기반으로 자동 정렬될 것입니다. |
| `classes` | 모듈에 필요한 클래스입니다. 이 필드는 필수가 아닙니다. |
| `header` | 모듈 바로 위에 표시되는 텍스트 값 입니다. 이 필드는 필수가 아닙니다. |
| `disabled` | 이 값을 `true`로 설정하면, 해당 모듈 객체의 생성을 건너 뜁니다. 즉, 해당 모듈을 실행하지 않습니다. 이 필드는 필수가 아닙니다. |
| `config` | 모듈이 참조할 configuration 속성 객체입니다. 모듈의 문서를 참조하여 더 많은 정보를 얻으세요. 이 필드는 필수가 아니지만, 모듈에 추가적인 설정이 필요하다면 작성하셔야 합니다. |

## 모듈

다음 모듈은 기본적으로 설치되어있습니다.

- [**시계(Clock)**](modules/default/clock)
- [**달력(Calendar)**](modules/default/calendar)
- [**현재 날씨(Current Weather)**](modules/default/currentweather)
- [**일기 예보(Weather Forecast)**](modules/default/weatherforecast)
- [**뉴스 피드(News Feed)**](modules/default/newsfeed)
- [**인사말(Compliments)**](modules/default/compliments)
- [**헬로, 월드(Hello World)**](modules/default/helloworld)
- [**알림(Alert)**](modules/default/alert)

더 많은 모듈을 확인하시려면, wiki page를 참조하세요: [MagicMirror² 모듈](https://github.com/MichMich/MagicMirror/wiki/MagicMirror²-Modules)
자신만의 모듈을 제작하고 싶으시다면, 다음 문서를 참조하세요: [MagicMirror² 모듈 제작 문서](modules)
모듈을 제작하고 난 뒤, wiki와 [forum](https://forum.magicmirror.builders/category/7/showcase)을 통한 추가를 잊지 마세요!

## 커뮤니티

MagicMirror²의 커뮤니티는 점차 발전하고 있습니다. 해당 [Forum](https://forum.magicmirror.builders)에서 여러분의 아이디어를 마음껏 공유하며, 궁금한 점에 대하여 질문하시고, 서로 도울 수 있는 환경이 될 수 있도록 노력해주시길 바랍니다!

## 기여 가이드라인

**참고:** 이 페이지의 [기여 가이드라인](#기여-가이드라인)은 원본 repository와 다르게 기능 및 버그 구현을 위한 기여가 아닌, 더 진보된 한글화를 위한 기여 가이드라인을 안내하고 있습니다.
모든 기여와 토론은 언제나 환영입니다! 맞춤법부터 내용상의 정리까지, 모든 기여와 수정을 적극 반영합니다!

pull request 혹은 issue를 생성할 때, 제목에 다음과 같은 머리말을 달아 빠르고 편한 기여가 가능하도록 도와주세요!
PR과 Issue에선 다음과 같은 머리말를 가질 수 있습니다.
- **문서 작성**: 아직 한글화가 이루어지지 않은 문서의 전체 혹은 일부분을 수정하실 때, 작성하실 수 있는 타이틀 태그입니다.
- **내용 수정**: 한글화가 이미 이루어진 문서 혹은 문구에 대한 **의미상의** 수정을 진행하실 때, 작성하실 수 있는 타이틀 태그입니다.
- **오탈자 수정**: 한글화가 이미 이루어진 문서 혹은 문구에 대한 **문법상의** 수정을 진행하실 때, 작성하실 수 있는 타이틀 태그입니다.

만약 동시에 1가지 이상의 작업이 진행되었다면, 해당하는 머리말를 전부 작성해주시길 바랍니다.
예시 제목: [문서 작성, 내용 수정] modules디렉토리의 default modules 메뉴얼 작성,수정 작업

MagicMirror² 한글화 프로젝트에 동참해주신 모두에게 고마움의 인사를 건냅니다!

<p align="center">
<br>
	<a href="https://forum.magicmirror.builders/topic/728/magicmirror-is-voted-number-1-in-the-magpi-top-50"><img src="https://magicmirror.builders/img/magpi-best-watermark-custom.png" width="150" alt="MagPi Top 50"></a>
</p>
