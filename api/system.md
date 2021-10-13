# love.system

<b><i>
시스템의 정보를 구하는 함수를 제공합니다.
</b></i>

## 함수

| 이름                                                                                | 설명                                                    | 비고                                                                                 |
|------------------------------------------------------------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------------------|
| [getOS](https://love2d.org/wiki/love.system.getOS_(한국어))                         | 현재 동작중인 OS를 구합니다                               |                                                                                      |
| [getProcessorCount](https://love2d.org/wiki/love.system.getProcessorCount_(한국어)) | 시스템의 CPU 코어 수를 구합니다                           |                                                                                      |
| [getPowerInfo](https://love2d.org/wiki/love.system.getPowerInfo_(한국어))           | 배터리를 사용하는 기기에서 전원 공급에 관한 정보를 구합니다 |                                                                                       |
| getNetworkInfo                                                                     | 시스템의 인터넷 상태를 구합니다                            |                                                                                      |
| getLanguage                                                                        | 콘솔 기기의 언어설정을 구합니다                            |                                                                                      |
| getRegion                                                                          | 콜솔 기기의 지역설정을 구합니다                            |                                                                                      |
| getModel                                                                           | 콘솔 기기의 모델을 구합니다                                | 예시로 N3DSXL, 3DS, Mariko, Erista가 있음                                             |
| getUsername                                                                        | 콘솔 기기나 앱의 현재 사용자를 구합니다                    | 스위치의 경우, 앱마다 다수의 계정으로 플레이 할수 있기 때문에 앱에 따라 결정됩니다          |
| getVersion                                                                         | 콘솔 기기의 펌웨어 버전을 구합니다                         |                                                                                      |
| getColorTheme                                                                      | 시스템의 현재 테마 컬러를 구합니다                         |                                                                                      |
| getFriendCode                                                                      | 현재 사용자의 친구코드를 구합니다                          |                                                                                      |
| getPlayCoins                                                                       | 시스템의 현재 플레이 코인을 개수를 구합니다                 | Nintendo 3DS 한정                                                                    |
| setPlayCoins                                                                       | 시스템의 플레이 코인 개수를 설정합니다                     | Nintendo 3DS 한정. 이 함수는 코인 개수를 추가하는 것이 아닙니다!!                        |
