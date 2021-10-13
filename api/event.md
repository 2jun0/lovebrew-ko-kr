# love.event

<b><i>
`love.handlers`라는 테이블을 추가하면 새 이벤트를 정의할 수 있습니다.<br>
테이블 색인을 인수로 하여 love.event.push로 이러한 함수를 호출할 수 있습니다.
</b></i>

## 함수

| 이름                                                    | 인자                        | 설명                              |
|---------------------------------------------------------|----------------------------|-----------------------------------|
| [clear (영문)](https://love2d.org/wiki/love.event.clear)|                            | 이벤트 큐를 지웁니다                |
| [pump (영문)](https://love2d.org/wiki/love.event.pump)  | `name`, `a`, `b`, `c`, ... | 이벤트 큐에서 이벤트를 펌핑합니다    |
| [push (영문)](https://love2d.org/wiki/love.event.push)  |                            | 이벤트 큐에 이벤트를 추가합니다      |
| [quit (영문)](https://love2d.org/wiki/love.event.quit)  |                            | 프로그램을 종료하거나 재시작 합니다  |