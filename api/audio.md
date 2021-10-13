# love.audio

<b><i>
소리 재생/녹음을 위한 오디오 인터페이스를 제공합니다.
</b></i>

## 함수

| 이름                                                               | 설명                                                     | 비고                                                   |
|--------------------------------------------------------------------|---------------------------------------------------------|--------------------------------------------------------|
| [getVolume](https://love2d.org/wiki/love.audio.getVolume_(한국어)) | 마스터 볼륨을 반환합니다                                  |                                                        |
| [newSource](https://love2d.org/wiki/love.audio.newSource_(한국어)) | 파일, 사운드 데이터 또는 디코더로 새 소스를 만듭니다        |                                                        |
| [pause](https://love2d.org/wiki/love.audio.pause_(한국어))         | 현재 재생되는 하나 또는 모든 소스를 일시중지합니다          |                                                        |
| [play](https://love2d.org/wiki/love.audio.play_(한국어))           | 하나 또는 여러 소스를 재생합니다                           |                                                        |
| [setVolume](https://love2d.org/wiki/love.audio.setVolume_(한국어)) | 마스터 볼륨을 설정합니다                                  |                                                        |
| [stop](https://love2d.org/wiki/love.audio.stop_(한국어))           | 현재 재생되는 하나 또는 모든 소스를 중지합니다              |                                                        |

<br>

## 타입

### Source

<b><i>
소스는 재생할 수 있는 오디오를 나타냅니다. 소스는 재생 중인 동안 내부적으로 참조됩니다.
</b></i>

더보기:
- [love.audio.newSource](https://love2d.org/wiki/love.audio.newSource_(한국어))
- [Object](api/love?id=Object)

| 이름                                                                         | 설명                                               | 비고                                                   |
|------------------------------------------------------------------------------|---------------------------------------------------|--------------------------------------------------------|
| [clone](https://love2d.org/wiki/Source:clone_(한국어))                        | 이 소스를 복제합니다                                |                                                        |
| [getChannelCount (영문)](https://love2d.org/wiki/Source:getChannelCount)      | 소스의 채널 수를 가져옵니다                         |                                                        |
| [getFreeBufferCount (영문)](https://love2d.org/wiki/Source:getFreeBufferCount)| 소스에서 사용 가능한 버퍼 개수를 가져옵니다           | 부분적으로만 구현됨.                                    |
| [getType (영문)](https://love2d.org/wiki/Source:getType)                      | 소스의 타입을 가져옵니다                            |                                                        |
| [getVolume](https://love2d.org/wiki/Source:getVolume_(한국어))                | 소스의 현재 볼륨을 가져옵니다                       |                                                        |
| [getVolumeLimits](https://love2d.org/wiki/Source:getVolumeLimits_(한국어))    | 소스의 볼륨 제한을 반환합니다                       |                                                        |
| [isLooping](https://love2d.org/wiki/Source:isLooping_(한국어))                | 소스의 루프 여부를 반환합니다                       |                                                        |
| [isPlaying](https://love2d.org/wiki/Source:isPlaying_(한국어))                | 소스의 재생 여부를 반환합니다                       |                                                        |
| [pause](https://love2d.org/wiki/Source:pause_(한국어))                        | 소스를 일시중지합니다                               |                                                        |
| [play](https://love2d.org/wiki/Source:play_(한국어))                          | 소스를 재생합니다                                  |                                                        |
| [seek](https://love2d.org/wiki/Source:seek_(한국어))                          | 소스의 현재 재생 위치를 설정합니다                   |                                                        |
| [setLooping](https://love2d.org/wiki/Source:setLooping_(한국어))              | 소스의 루프 여부를 설정합니다                       |                                                        |
| [setVolume](https://love2d.org/wiki/Source:setVolume_(한국어))                | 소스의 현재 볼륨을 설정합니다                       |                                                        |
| [setVolumeLimits](https://love2d.org/wiki/Source:setVolumeLimits_(한국어))    | 소스의 볼륨 제한을 설정합니다                       |                                                        |
| [stop](https://love2d.org/wiki/Source:stop_(한국어))                          | 소스를 중지합니다                                  |                                                        |

<br>
