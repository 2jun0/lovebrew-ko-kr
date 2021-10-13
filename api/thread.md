# love.thread

<b><i>
멀티 스레딩을 제공하는 모듈입니다.

스레드는 메인 코드로부터 Lua 환경을 분리해 병렬적으로 실행됩니다. 이로서 메인 코드의 프레임 레이트를 감소시키는 일 없이 복잡한 연산을 효과적으로 수행할 수 있습니다. 그러나 분리된 환경은 메인 스레드의 변수나 함수에 접근할 수 없고, 각 스레드 간 통신 또한 자유롭지 못하기 때문에 각별한 주의가 필요합니다.

LOVE에서 제공하는 객체(또는 유저데이터)들은 모든 스레드에서 공유되기 때문에 이들을 다른 스레드에서 사용하려면 객체 내용을 통째로 복사할 필요가 없이 오직 참조만 전달하면 됩니다. 물론 동시에 여러 스레드에서 같은 객체에 접근할 경우 동기화 관련 문제가 발생할 수 있습니다.

스레드는 시작되면서 love.thread 모듈만을 로드합니다. 다른 모든 모듈은 require선언을 통해 명시적으로 불러서 사용해야 합니다.
<b></i>

## 함수

| 이름                                                                  | 설명                                                                        | 비고 |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------|------|
| [newThread](https://love2d.org/wiki/love.thread.newThread_(한국어))   | 루아 스크립트나 FileData로부터 새로운 스레드를 생성합니다                       |      |
| [newChannel](https://love2d.org/wiki/love.thread.newChannel_(한국어)) | 이름 없는 스레드 채널을 생성합니다                                             |      |
| [getChannel](https://love2d.org/wiki/love.thread.getChannel_(한국어)) | 이름 있는 스레드 채널을 생성하거나 얻어옵니다                                   |      |

## 타입

### Thread

<b><i>
스레드를 표현하는 타입입니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [love.thread.newThread](https://love2d.org/wiki/love.thread.newThread_(한국어))

| 이름                                                           | 설명                                             | 비고 |
|----------------------------------------------------------------|-------------------------------------------------|-------|
| [start](https://love2d.org/wiki/Thread:start_(한국어))         | 스레드를 실행합니다                                |     |
| [wait](https://love2d.org/wiki/Thread:wait_(한국어))           | 스레드가 완료되기를 기다립니다                      |     |
| [getError](https://love2d.org/wiki/Thread:getError_(한국어))   | 스레드에서 에러가 발생되었을 경우 메시지를 반환합니다 |     |
| [isRunning](https://love2d.org/wiki/Thread:isRunning_(한국어)) | 스레드가 현재 실행중인지 확인합니다                  |     |

### Channel

<b><i>
서로 다른 스레드 사이에 데이터를 주고받는 데 사용되는 객체입니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [love.thread.newChannel](https://love2d.org/wiki/love.thread.newChannel_(한국어))

| 이름                                                                  | 설명                                                                              | 비고  |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------|-------|
| [push](https://love2d.org/wiki/Channel:push_(한국어))                 | 채널로 메시지를 전송합니다                                                          |      |
| [supply](https://love2d.org/wiki/Channel:supply_(한국어))             | 채널로 메시지를 전송한 후, 다른 스레드가 메시지를 받을 때까지 대기합니다                |      |
| [pop](https://love2d.org/wiki/Channel:pop_(한국어))                   | 채널에서 메시지를 얻어온 후 메시지 큐에서 메시지를 삭제합니다                          |      |
| [demand](https://love2d.org/wiki/Channel:demand_(한국어))             | 채널에 메시지가 도착할 때까지 무한정 기다린 후 메시지가 도착하면 메시지를 얻어옵니다     |      |
| [peek](https://love2d.org/wiki/Channel:peek_(한국어))                 | 채널에서 메시지를 얻어옵니다만, 메시지 큐에서 삭제하지는 않습니다                       |      |         
| [getCount](https://love2d.org/wiki/Channel:getCount_(한국어))         | 메시지 큐에 메시지가 몇 개나 쌓여있는지 세어봅니다                                     |      |
| [hasRead (영문)](https://love2d.org/wiki/Channel:hasRead)             | 푸시된 값이 팝(pop)되었는지 또는 채널에서 제거되었는지 여부를 가져옵니다                |      |
| [clear (영문)](https://love2d.org/wiki/Channel:clear)                 | 채널 큐의 모든 메시지를 지웁니다                                                     |      |
| [performAtomic (영문)](https://love2d.org/wiki/Channel:performAtomic) | 이 채널과 관련된 함수를 독립적으로 실행합니다                                         |      |