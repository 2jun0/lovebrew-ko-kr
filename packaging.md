?> 아래의 내용은 중요한 정보이니 꼼꼼하게 보셔야 합니다. 또한 필요하다면 다른 링크를 타고 더 자세히 읽어보십시오.

## 전제조건

[개발 환경 설정](building?id=getting-started)에 대한 지침을 따르세요.

## 방법

?> 닌텐도 스위치에서는 Atmosphère의 타이틀 테이크오버 기능을 사용하십시오. 이를 통해 당신의 게임이 소프트웨어 키보드를 포함한 허용된 모든 시스템 메모리를 사용할 수 있습니다. 닌텐도 3DS의 경우 일반 홈브류 메뉴를 사용하십시오. 우리는 cia 또는 "설치 가능한" nsp 파일 빌드를 지원하지 않습니다.

### 서문

LÖVE Potion이 실행되면 먼저 자신의 *RomFS(읽기 전용 파일 시스템)* 내에서 게임을 찾으려고 할 것입니다. 스탠드얼론 방식(커스텀 메타데이터에 유용)으로 LÖVEBrew로 게임을 빌드하지 않은 경우, 기본적으로 '게임 폴더'를 사용할 것입니다. 위치를 찾지 못하면 'No Game'이 화면에 표시됩니다.

당신의 LÖVE Potion 프로젝트를 기억하기 쉬운 디렉터리에 보관하세요. `devkitPro` 폴더에 **_절대_** LÖVE Potion 데이터, 게임, **_또는_** 다른 바이너리를 **_넣지 마십시오_**. 데스크톱이나 Dropbox와 같은 클라우드 스토리지에 보관하세요.

LÖVEBrew 애플리케이션에 더 많은 정보를 얻고 싶다면 [여기를 참고하세요](lovebrew)

### LÖVE 실행 파일

!> 이 방법은 닌텐도 3DS 버전에 적용되지 않습니다.

[공식 LÖVE 위키](https://love2d.org/wiki/Game_Distribution#Create_a_.love-file)에서 '`love` 파일을 만드는 법'을 참고하세요.

LÖVE 바이너리가 생성되면, [config.zip 파일을 다운로드](files/config.zip ':ignore')하세요. 그후 config.zip 내 `lovepotion.cfg` 파일을 스위치 마이크로 SD 카드 `/nx-hbmenu/config/fileassoc`에 복사하세요. `LovePotion` 폴더가 `/switch` 안에 있을 수도 있습니다. LÖVE Potion의 최신 사본만 누락된 것이니 [최신 *.nro 바이너리](https://github.com/TurtleP/LovePotion/releases)를 다운로드하여 `LovePotion` 폴더에 저장하세요.

마지막으로 새 *SuperGame.love* 파일을 마이크로 SD 카드의 `/switch` 폴더에 넣고 홈브류 메뉴를 여세요. 이제 실행할 수 있는 항목으로 표시됩니다.

### 'Game' 폴더

?> 이는 게임을 개발하기 위한 것입니다. 모든 작업이 완료되면 이전 방법 중 하나를 사용하십시오. 사용자 지정 게임 아이콘 및 제목/작가를 원할 경우, lovebrew 응용 프로그램을 사용하여 패키지화하십시오.

디버그를 위한 가장 빠른 방법은 `game` 폴더를 통한 것입니다. [최신 *.nro 혹은 *.3dsx 바이너리](https://github.com/TurtleP/LovePotion/releases)파일을 다운로드하고 `/switch/LovePotion`(혹은 `/3ds/LovePotion`) 안에 넣으세요. `LovePotion` 디렉터리가 없다면 새로 생성하면 됩니다.

`/switch/LovePotion`(혹은 `/3ds/LovePotion`)안에 `game` 디렉터리를 만드세요. 여기에 모든 소스파일을 담으세요. 닌텐도 3DS에서는 텍스처와 글꼴을 특수 형식으로 변환해야 합니다. `tex3ds`와 `mkbcfnt`를 사용하여 수동으로 변환할 수 있지만 [LÖVEBrew 애플리케이션](lovebrew)에서 `raw`구성 항목을 `true`로 설정하는 방식이 제일 쉽습니다. 모든 작업이 완료되면 홈브류 메뉴를 열고 LÖVE Potion 항목을 실행하면 게임이 실행됩니다!