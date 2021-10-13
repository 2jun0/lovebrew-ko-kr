# love.sound

<b><i>
사운드 파일을 읽어들이는 모듈입니다. 이 모듈은 사운드를 재생하지는 못합니다. 실제 동작은 [love.audio](ko-kr/api/love.audio)에서 합니다.
효과음같은 짧은 사운드는 SoundData, 배경음같은 긴 사운드는 Decoder를 사용하는 것이 좋습니다. 왜 그런지에 대한 이유는 각 타입을 참조하세요.
</b></i>

## 함수

| 이름                                                                     | 설명                                                                         | 비고 |
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------|-------|
| [newDecoder](https://love2d.org/wiki/love.sound.newDecoder_(한국어))     | 정한 사운드 파일의 포맷에 대응되는 Decoder를 생성합니다                          |      |
| [newSoundData](https://love2d.org/wiki/love.sound.newSoundData_(한국어)) | 새로운 SoundData를 생성합니다                                                  |      |

## 타입

### Decoder

<b><i>
사운드 파일을 디코딩하는 객체입니다. 파일의 확장자로부터 오디오 포맷(MP3, Ogg Vorvis, 압축된 WAVE)을 추정하여 이에 대응되는 디코딩 알고리즘을 선정하고, 실제 오디오 파일이 재생되었을 때 선정한 알고리즘을 이용해 디코딩합니다.
디코더는 자원을 절약하기 위해 매우 효율적으로 동작합니다. 파일을 일정한 크기로 쪼갠 후, Source에 의해 오디오가 재생될 때 재생되고 있는 부분에 맞추어 파일 조각을 읽어들입니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [love.sound.newDecoder](https://love2d.org/wiki/love.sound.newDecoder_(한국어))

| 이름                                                                        | 설명                                                | 비고  |
|----------------------------------------------------------------------------|----------------------------------------------------|-------|
| [clone (영문)](https://love2d.org/wiki/Decoder:clone)                       | 기존의 Decoder를 복제합니다                          |       |
| [getChannelCount](https://love2d.org/wiki/Decoder:getChannelCount_(한국어)) | 채널 수를 구합니다                                  |       |
| [getBitDepth](https://love2d.org/wiki/Decoder:getBitDepth_(한국어))         | 샘플 당 비트 수를 구합니다                           |       |
| [getSampleRate](https://love2d.org/wiki/Decoder:getSampleRate_(한국어))     | 샘플 레이트를 구합니다                               |       |
| [getDuration (영문)](https://love2d.org/wiki/Decoder:getDuration)           | 소리 파일의 재생길이를 구합니다                       |       |
| [decode (영문)](https://love2d.org/wiki/Decoder:decode)                     | 오디오 데이터 청크를 SoundData로 디코딩합니다         |       |
| [seek (영문)](https://love2d.org/wiki/Decoder:seek)                         | Decoder의 현재 재생위치를 설정합니다                  |       |

### SoundData

<b><i>
실제 오디오 데이터를 메모리에 가지고 있는 객체입니다.
객체 생성 즉시 사운드 파일을 전부 메모리에 올립니다. 따라서 실제 재생되고 있는 위치에 따라 부분부분 메모리에 등재하는 디코더와는 달리 빠른 반응속도를 기대할 수 있습니다. 그러나 파일이 통째로 메모리에 올라가기 때문에 너무 큰 파일을 SoundData로 불러들이는 것은 메모리를 과도하게 차지할 수도 있습니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [Data](ko-kr/api/data)
- [love.sounds.newSoundData](https://love2d.org/wiki/love.sound.newSoundData_(한국어))

| 이름                                                                          | 설명                                                        | 비고  |
|------------------------------------------------------------------------------|-------------------------------------------------------------|-------|
| [clone (영문)](https://love2d.org/wiki/SoundData:clone)                       | 기존 SoundData를 복제합니다                                   |       |
| [getBitDepth](https://love2d.org/wiki/SoundData:getBitDepth_(한국어))         | 샘플 당 비트 수를 구합니다                                    |       |
| [getChannelCount](https://love2d.org/wiki/SoundData:getChannelCount_(한국어)) | 채널 수를 구합니다                                           |       |
| [getDuration](https://love2d.org/wiki/SoundData:getDuration_(한국어))         | 총 재생 시간을 구합니다                                       |       |
| [getSampleCount](https://love2d.org/wiki/SoundData:getSampleCount_(한국어))   | 샘플 수를 구합니다                                           |       |
| [getSampleRate](https://love2d.org/wiki/SoundData:getSampleRate_(한국어))     | 샘플 레이트를 구합니다                                        |       |
| [setSample](https://love2d.org/wiki/SoundData:setSample_(한국어))             | 특정 위치의 샘플을 설정합니다                                 |       |
| [getSample](https://love2d.org/wiki/SoundData:getSample_(한국어))             | 특정 위치의 샘플을 구합니다                                   |       |
