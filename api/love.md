# love

## 함수

| 이름       | 설명                                                       |
|------------|-----------------------------------------------------------|
| getVersion | 앱과 호환되는 LÖVE 버전을 반환합니다                         |

<br>

## 상수

| 이름              | 설명                                                                |
|-------------------|--------------------------------------------------------------------|
| _os               | 실행 중인 OS("Horizon")을 반환합니다                                 |
| _version          | 앱과 호환되는 LÖVE 버전을 반환합니다                                  |
| _potion_version   | LÖVE Potion 버전을 반환합니다                                        |
| _console_name     | 실행 중인 콘솔기기("3DS" 혹은 "Switch")를 반환합니다                  |
| _version_major    | 앱과 호환되는 LÖVE의 메이저 버전을 반환합니다                         |
| _version_minor    | 앱과 호환되는 LÖVE의 마이너 버전을 반환합니다                         |
| _version_revision | 앱과 호환되는 LÖVE의 수정 버전을 반환합니다                           |
| _version_codename | 앱과 호환되는 LÖVE의 코드 이름을 반환합니다                           |

<br>

## 콜백함수

| 이름            | 인자                                   | 설명                                                       |
|-----------------|----------------------------------------|-----------------------------------------------------------|
| load            | `args`                                 | 앱 로드 시 호출됩니다                                       |
| update          | `dt`                                   | 프레임당 한 번씩 호출됩니다, 대게 1/60 입니다                |
| draw            | `screen`¹                              | 프레임당 한 번씩 호출됩니다, 스크린에 렌더링 하는데 사용됩니다 |
| focus           | `focused`                              | 앱이 일시 중단되거나 중단되지 않은 경우 호출됩니다            |
| gamepadpressed  | `joystick`, `button`                   | 시스템이 버튼 입력을 수신하면 호출됩니다                     |
| gamepadreleased | `joystick`, `button`                   | 시스템이 버튼 입력 수신을 중지하면 호출됩니다                 |
| gamepadaxis     | `joystick`, `axis`, `button`           | 시스템이 스틱 컨트롤러 입력을 수신하면 호출됩니다             |
| touchpressed    | `id`, `x`, `y`, `dx`, `dy`, `pressure` | 시스템이 터치 스크린 입력을 수신하면 호출됩니다               |
| touchreleased   | `id`, `x`, `y`, `dx`, `dy`, `pressure` | 시스템이 터치 스크린 입력 수신을 중지하면 호출됩니다          |
| touchmoved      | `id`, `x`, `y`, `dx`, `dy`, `pressure` | 터치 스크린 입력 이동을 수신하면 호출됩니다                   |
| textinput       | `text`                                 | 소프트웨어 키보드 사용이 완료되면 호출됩니다                  |
| errhand         | `message`                              | 앱이 Lua 스크립트 오류를 수신하면 호출됩니다                 |
| errorhandler    | `message`                              | 앱이 Lua 스크립트 오류를 수신하면 호출됩니다                 |
| threaderror     | `Thread`, `message`                    | `Thread` 개체에 오류가 발생하면 호출됩니다                   |
| quit            |                                        | 게임이 종료되려고 할 때 호출됩니다                           |

<br>

## 서드-파티 모듈

- [socket (영문)](https://love2d.org/wiki/socket)
- [utf8 (영문)](https://love2d.org/wiki/utf8)

## 타입

### Object

**_모든 LÖVE 타입의 슈퍼클래스_**

### 함수

| 이름                                                       | 설명                                             |
|------------------------------------------------------------|-------------------------------------------------|
| [release (영문)](https://love2d.org/wiki/Object:release)   | 객체의 Lua 참조를 즉시 삭제합니다                  |
| [type](https://love2d.org/wiki/Object:type_(한국어))       | 객체의 타입을 문자열로 가져옵니다                  |
| [typeOf](https://love2d.org/wiki/Object:typeOf_(한국어))   | 객체가 특정 타입인지 확인합니다                    |

<br>

### [변수 (영문)](https://love2d.org/wiki/Variant)

<br>

¹닌텐도 3DS 한정. `left`, `right`, `bottom`중 하나의 값.

더 자세한 정보를 보려면 [공식 LÖVE 위키](https://love2d.org/wiki/love_(한국어)#콜백_함수)를 참고하세요.