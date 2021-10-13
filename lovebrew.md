!> 필요한 도구를 아직 설정하지 않은 경우 [빌드 섹션](ko-kr/building?id=시작하기)을 따라 설정하세요!

### 환경 설정

콘솔용 [최신 릴리즈 LÖVE Potion](https://github.com/lovebrew/LovePotion/releases)을 다운로드하고 기억할 수 있는 공간에 저장하세요. zip파일 안에 2개의 파일이 있지만 확장자가 *.elf인 파일만 다루세요. 기기에 따라 이름을 `3DS.elf`또는 `Switch.elf`로 변경한 다음, 파일을 구성 디렉터리에 복사하십시오.

* Windows: `%appdata%\lovebrew`
* Linux/macOS: `~/.config/lovebrew`

그런 다음 플랫폼에 대한 [최신 릴리즈 LÖVE Potion](https://github.com/lovebrew/LovePotion/releases)을 다운로드하고 앞서 언급한 디렉터리에 복사합니다. Windows사용자는 `PATH`환경 변수에 이 디렉터리를 추가해야 합니다.

커맨드 라인에서 `lovebrew`를 실행해서 최초 메시지를 출력해보세요.

### 디렉터리 구조

LÖVEBrew를 사용할 때의 일반적인 구조는 다음과 같습니다.

```
SuperProject
├── SuperGame
│   ├── conf.lua
│   └── main.lua
└── lovebrew.toml
```

`SuperProject`는 프로젝트의 이름으로 불릴 최상위 폴더입니다. `SuperGame`는 빌드 과정에서 사용될 모든 게임 에셋을 담을 디렉터리 입니다. `lovebrew.toml` 파일은 `lovebrew init`를 실행하면 `SuperProject` 디렉터리 안에 생깁니다. 여기서 여러 가지의 설정을 변경할 수 있습니다. 더 중요한 설정은 아래에 자세히 설명되어 있습니다.

### 사용자 정의 메타데이터 & 아이콘

`lovebrew.toml` 파일은 Windows의 메모장을 포함한 (Windows에서 파일을 열 대상을 묻는 메시지가 표시되더라도 메모장을 계속 사용할 수 있습니다) 텍스트 에디터로 열 수 있습니다. 항목별로 주석이 있으니 잘 읽어보세요. 모든 `string` 값은 공백을 포함할 수 있습니다.

사용자 지정 아이콘을 원한다면 닌텐도 3DS의 경우 48x48의 `*png` 이미지를 만들어야 합니다. 닌텐도 스위치 버전의 경우, 256x256의 `*.jpg`이미지를 만들어야 합니다. 스위치의 아이콘에 문제가 있다면 저장할때 `progressive` 플래그를 해제해야 할 수도 있습니다. GIMP같은 몇몇 프로그램들은 이것을 도와줍니다. 사용자 지정 아이콘이 없다면 LÖVEBrew는 기본 아이콘을 사용합니다.

### 프로젝트 빌드

모두 끝난 후, `lovebrew build`를 실행하세요.

닌텐도 3DS에선 이 명령이 필요에 따라 에셋을 변환시킬 것입니다.

새로 빌드된 *SuperGame.(nro/3dsx)*를 마이크로 SD카드 안에 자체 명명된 디렉터리, *SuperProject* 디렉터리, 또는 결과 바이너리 디렉터리 내 `/switch`(혹은 `/3ds`)에 복사합니다. 홈브류 메뉴를 열면 항목으로 표시될 것입니다.