# love.joystick

<b><i>
조이스틱 조작에 필요한 함수를 제공합니다. 일관적인 처리를 위해 조이스틱을 가상 게임패드(Xbox 360 컨트롤러)에 대응시켜 사용할 수 있습니다.
</b></i>

?> 3DS 콘솔 기기의 조이스틱은 하나만 인식됩니다.

## 함수

| 이름                                                                               | 설명                                    | 비고        |
|------------------------------------------------------------------------------------|----------------------------------------|-------------|
| [getJoystickCount](https://love2d.org/wiki/love.joystick.getJoystickCount_(한국어)) | 연결된 조이스틱의 개수를 구합니다         |             |
| [getJoysticks](https://love2d.org/wiki/love.joystick.getJoysticks_(한국어))         | 연결된 조이스틱 리스트를 얻어옵니다       |             |
| split                                                                              | 조이콘 쌍을 둘로 나눕니다                 |  스위치 전용 |
| merge                                                                              | 두개의 나누어진 조이콘을 하나로 합칩니다   |  스위치 전용 |

## 타입

### Gamepad

<b><i>
물리 조이스틱 조작에 필요한 함수를 제공합니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)

| 이름                                                                                 | 설명                                                                          | 비고  |
|--------------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------|
| [getAxes (영문)](https://love2d.org/wiki/Joystick:getAxes)                           | 각 축의 방향을 가져옵니다                                                      |       |
| [getAxis (영문)](https://love2d.org/wiki/Joystick:getAxis)                           | 하나의 축의 방향을 가져옵니다                                                   |       |
| [getButtonCount (영문)](https://love2d.org/wiki/Joystick:getButtonCount)             | 조이스틱의 버튼 넘버를 가져옵니다                                               |       |
| [getGamepadAxis (영문)](https://love2d.org/wiki/Joystick:getGamepadAxis)             | 가상 게임패드 축의 방향을 가져옵니다                                            |       |
| [getID (영문)](https://love2d.org/wiki/Joystick:getID)                               | 조이스틱의 고유 식별자를 가져옵니다                                             |       |
| [getName (영문)](https://love2d.org/wiki/Joystick:getName)                           | 조이스틱의 이름을 가져옵니다                                                    |       |
| [getVibration (영문)](https://love2d.org/wiki/Joystick:getVibration)                 | 진동모터가 있는 조이스틱에서 현재 모터 강도를 가져옵니다                          |       |
| [isConnected (영문)](https://love2d.org/wiki/Joystick:isConnected)                   | 조이스틱이 연결되었는지를 구합니다                                               |       |
| [isDown (영문)](https://love2d.org/wiki/Joystick:isDown)                             | 조이스틱의 버튼이 눌렸는지 확인합니다                                            |       |
| [isGamepad (영문)](https://love2d.org/wiki/Joystick:isGamepad)                       | 조이스틱이 게임패드로 인식되는지 여부를 구합니다                                  |       |
| [isGamepadDown (영문)](https://love2d.org/wiki/Joystick:isGamepadDown)               | 조이스틱의 가상 게임패드 버튼이 눌린 여부를 구합니다                              |       |
| [isVibrationSupported (영문)](https://love2d.org/wiki/Joystick:isVibrationSupported) | 조이스틱이 진동을 지원하는지 여부를 가져옵니다                                   |       |
| [setVibration (영문)](https://love2d.org/wiki/Joystick:setVibration)                 | 진동모터가 있는 조이스틱에서 진동 모터 속도를 설정합니다                          |       |