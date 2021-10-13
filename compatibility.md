!> LÖVE Potion은 현재 개발 중이기 때문에 일부가 누락되었을 수 있습니다. 요청하고 싶은 기능이 있으면 [깃허브 저장소](https://github.com/TurtleP/LovePotion)에서 이슈를 여십시오.

## 그리기

!> 완성적이고 안정적인 2.0.0버전 출시 이전에, 문자열이 단순히 `top` 혹은 `bottom`이였습니다. 이는 최종 릴리스에서 3D 깊이 기능 변경으로 수정되었습니다.

닌텐도 3DS에서는 큰 어려움이 있었습니다. 초기 코드베이스에선 `love.graphics.setScreen(screen)`에 의존했지만, 현재 버전 2.0.0은 `love.draw` 콜백에 `screen` 매개변수가 생겼습니다. 닌텐도 스위치 버전에선 이 문제에 대해서 상관이 없습니다.

매개변수로 전달되는 `screen`값으로 쉽게 어떤 스크린인지 확인할 수 있습니다.

```lua
function love.draw(screen)
    if screen ~= "bottom" then
        -- render top screen
    end
end
```

현재 `screen` 매개변수는 `left`혹은 `right`, `bottom`세 문자열 중 하나로 전달됩니다. `left`와 `right`는 상단에 있는 화면으로 3D 깊이 기능과 관련되어 있습니다. 

또한, 텍스쳐(png, jpg 파일)는 `tex3ds`을 사용해서 닌텐도 3DS에서 t3x 포맷으로 변경해야 합니다. devkitpro-pacman에서 제공하고 있으니 [개발환경 설정하기](https://turtlep.github.io/LovePotion/wiki/#/packaging?id=전제조건)에서 자세한 정보를 참고하세요.

## 시스템 글꼴 불러오기

`love.graphics.newFont`의 매개변수로 경로 대신에 아래의 이름를 사용해서 시스템 글꼴를 불러올 수 있습니다.

### 닌텐도 3DS

| 이름      | 비고                               |
|-----------|-------------------------------------|
| standard  | 일본, 미국, 유럽, 호주 지역 글꼴  |
| chinese   | 중국어 글꼴                        |
| korean    | 한국어 글꼴                         |
| taiwanese | 대만 글꼴                      |

### 닌텐도 스위치

| 이름                        | 비고                               |
|-----------------------------|-------------------------------------|
| standard                    | 일본, 미국, 유럽, 호주 지역 글꼴 |
| chinese simplified          | 간체자 중국어 글꼴             |
| chinese traditional         | 번체자 중국어 글꼴            |
| extended chinese simplified | 확장된 간체자 중국어 글꼴    |
| korean                      | 한국어 글꼴                         |
| nintendo extended           | 닌텐도 확장 기호 글꼴      |

사용자 지정 글꼴의 경우 `mkbcfnt`를 사용하여 TrueType 또는 OpenType 글꼴을 bfnt로 변환해야 합니다. devkitpro-pacman에서 제공하고 있으니 [개발환경 설정하기](https://turtlep.github.io/LovePotion/wiki/#/packaging?id=전제조건)에서 자세한 정보를 참고하세요. 닌텐도 3DS의 스탠다드(standard) 글꼴은 Play Coin 아이콘과 같은 다양한 기호들에 대한 글리프(glyph) 데이터를 보유하고 있습니다. 하지만, 다음과 같이 이 글자들은 닌텐도 스위치의 닌텐도 확장 기호 글꼴에 저장됩니다.

```lua
local utf8 = require("utf8")

-- Play Coin 아이콘의 인코딩된 utf8을 가져옵니다.
local glyph = utf8.char("0xE075")

function love.load()
    -- 스위치를 사용하는 경우 확장 글꼴을 현재 글꼴로 설정합니다.
    if love._console_name == "Switch" then
        love.graphics.setNewFont("nintendo extended", 14)
    end
end

function love.draw(screen)
    -- 상단(top)만 렌더링 합니다.
    -- 3DS용 스크린과 상관없이 스위치에서 렌더링됩니다.
    if (screen and screen ~= "top") then
        return
    end

    love.graphics.print(glyph)
end
```

## 확장 시스템 함수

닌텐도 3DS와 닌텐도 스위치가 우리의 기본적인 LÖVE 환경과 약간 다르기 때문에 아래의 `system`모듈 함수가 추가되었습니다.

* `love.system.getNetworkStatus()`
    - 시스템 인터넷 연결 여부를 반환합니다.
* `love.system.getUsername()`
    - LÖVE Potion(또는 기본 게임)을 플레이하는 사용자의 이름을 반환합니다.
* `love.system.getLanguage()`
    - 현재 시스템 언어를 문자열로 반환합니다.

특히 UI, netplay 또는 다국어 지원에 유용합니다!

## 콘솔-전용 상수

LÖVE Potion의 3DS와 스위치 버전 모두 아래의 상수들이 있습니다.

* `love._console_name`
    - 콘솔 이름 "3DS" 또는 "Switch"를 반환합니다.
* `love._potion_version`
    - LÖVE Potion의 버전을 반환합니다.

## 소프트웨어 키보드

`love.keyboard.setTextInput`을 호출하면 시스템 소프트웨어 키보드 애플릿이 나타납니다. 테이블을 전달하여 설정합니다.

| 설정     | 비고                                   |
|------------|-----------------------------------------|
| type       | basic, numpad, standard<sup>1</sup> |
| isPassword | 입력 후 텍스트를 숨깁니다.       |
| hint       | 입력 시 보여줄 텍스트         |

<sup>1</sup> 닌텐도 스위치 한정

## 게임패드 상수

?> LÖVE Potion는 `love.gamepad*`콜백만을 입력 핸들링(조이콘 또는 3DS 시스템 자체에 포함)으로 사용합니다. 버튼 이름 목록에 대해선 [공식 LÖVE 위키](https://love2d.org/wiki/GamepadButton_(한국어))를 참고하십시오.

### 닌텐도 3DS

![닌텐도 3DS 컨트롤러 키 매핑](files/3DSControllerMap.png)

### 닌텐도 스위치

![닌텐도 스위치 컨트롤러 키 매핑](files/SwitchControllerMap.png)

## 기타

### 닌텐도 3DS

!> 입체심도는 닌텐도 2DS 시리즈에서 사용할 수 없으며 항상 0을 반환할 것입니다. 그럼에도 3D 깊이를 테스트 하려한다면 3DS 시스템을 가진 사람에게 도움을 요청하십시오.

닌텐도 3DS는 입체 3D로 3D 안경 없이도 상단 화면에서 3D 효과를 사용할 수 있습니다. 이를 제어하려면 `love.graphics.getStereoscopicDepth()`를 사용하세요. 0부터 1까지 범위의 3D 슬라이더 값이 반환됩니다. 다음의 예시를 참고하세요.

```lua
local str, font = "Hello World", nil
local textDepth = 6
function love.load()
    font = love.graphics.getFont()
end

function love.draw(screen)
    if screen == "bottom" then
        return
    end

    local sysDepth = -love.graphics.getStereoscopicDepth()

    if screen == "right" then
        sysDepth = -sysDepth
    end

    local left = math.floor(0.5 * (400 - font:getWidth(str)))
    love.graphics.print("Hello World", left - sysDepth * textDepth, 120)
end
```

## 게임 디버깅

?> 이 섹션이 업데이트가 된 이유가 궁금하십니까? [FAQ를 확인하십시오](faq?id=게임-디버깅하는-데-왜-이렇게-오래-걸려요)!

LöVE Potion 게임의 디버깅은 항상 큰 골칫거리였다. 특히 닌텐도 스위치에서는 복잡한 문제로 툴체인 제공 콘솔을 사용할 수 없었습니다. 그러나, 사용자들은 이제 프린트 출력을 위해 스위치에서 nxlink를 사용할 수 있고 심지어 3DS의 gdb 디버거도 사용할 수 있다. 간단히 conf.lua 안에서 콘솔 플래그를 활성화하라!

LÖVE Potion 게임의 디버깅은 항상 큰 골칫거리였습니다. 특히 닌텐도 스위치에서는 복잡한 문제로 콘솔 제공 툴체인을 사용할 수 없었습니다. 하지만, 사용자들은 이제 스위치에서 `nxlink`를 비롯해 3DS의 gdb 디버거까지 `print`출력에 사용할 수 있게 되었습니다. [`conf.lua`](https://love2d.org/wiki/Config_Files_(한국어))에서 콘솔 플래그를 활성화 하기만 하면 됩니다!

### 닌텐도 3DS

이는 좀 더 깊고 복잡하지만, 개발자들은 [개발 환경 설정](building?id=시작하기)를 따라야 합니다. devkitpro-pacman이 설치되면 3DS gdb 컴포넌트들을 설치하세요.

<!-- tabs:start -->

#### **Windows (msys2)**

```bash
pacman -S devkitARM-gdb
```

#### **Unix-like (Linux, macOS)**

```bash
sudo (dkp-)pacman -S devkitARM-gdb
```

설치가 완료되면 hbmenu로 이동합니다. rosalina menu combo(기본값 `L + R + Down + Select`)를 실행하고 "debugger options"을 입력한 다음 "Enable Debugger"에서 `a`를 누릅니다. 디버거에 할당된 IP 및 포트를 기록해 두십시오! 되돌아가려면 `b`를 누르고 "Force-debug next application at launch"를 선택합니다. LÖVE Potion을 선택한 다음 터미널에 `/opt/devkitpro/devkitARM/bin/arm-none-eabi-gdb`를 입력하고 enter 키를 누릅니다. 다음으로 `target remote ip:port`를 입력합니다. (여기서 ip와 port는 전에 기록해둔 디버거의 정보입니다.) 디버깅이 시작되고 실행된 모든 `print`호출이 터미널의 창으로 출력될 것입니다.

### 닌텐도 스위치

`nxlink`가 `switch-tools`패키지와 함께 제공되기 때문에 `y`를 누르고 `nxlink -s path/to/nro`를 실행하는 터미널에서 netsender를 hbmenu에서 로드하기만 하면됩니다. 스위치가 nro를 수신하고 나서 다운로드가 완료되면 즉시 실행됩니다. 실행된 모든 `print`호출이 터미널의 창으로 출력될 것입니다.

### 대안

*절대적인* 최고의 경험을 위한 유일한 대안은 LÖVE 자체를 사용하는 것입니다. 컨트롤러를 연결하고 [nëst 라이브러리](https://github.com/TurtleP/nest)를 사용하세요. 물론 LÖVE Potion의 일부 기능이 사용 불가능 하니 유의하세요.