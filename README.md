## 반가워요 ♥

LÖVE Potion은 닌텐도3DS와 닌텐도 스위치를 위한 홈브류(homebrew) 게임 프레임 워크입니다.

LÖVE 혹은 Lua언어를 잘 모르신다면, 사이드바의 "LÖVE 하는 방법"링크를 먼저 클릭하는 걸 추천드립니다.

LÖVE의 사용 방식을 이해했으면 [호환성](ko-kr/compatibility) 섹션에서 LÖVE Potion의 특성을 확인하십시오. 사이드바에서 현재 API 참조를 볼 수도 있습니다.

![LÖVE Potion 로고](../files/lovepotion.png)

## Hello World
아래는 LÖVE Potion에서 'hello world'를 출력하는 예제입니다.

```lua
function love.draw()
    love.graphics.print('Hello World!', 200, 120)
end

-- 버튼이 눌렸을 때, 앱이 종료되게 합니다.
function love.gamepadpressed(joystick, button)
    love.event.quit()
end
```
