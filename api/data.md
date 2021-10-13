# love.data

<b><i>
데이터 생성 및 변환 기능을 제공합니다.
</b></i>

## 함수

| 이름                                                                   | 설명                                                                                                                             |
|------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| [newByteData (영문)](https://love2d.org/wiki/love.data.newByteData)     | 지정한 문자열 또는 기존 ByteData 객체의 내용을 복사하여 새 ByteData 개체를 만듭니다                                                  |
| [compress (영문)](https://love2d.org/wiki/love.data.compress)           | 특정 압축 알고리즘을 사용하여 문자열 또는 data를 압축합니다                                                                         |
| [decompress (영문)](https://love2d.org/wiki/love.data.decompress)       | 압축된 문자열 또는 CompressedData, Data 객체를 압축해제합니다                                                                      |
| [decode (영문)](https://love2d.org/wiki/love.data.decode)               | Data 또는 문자열을 [EncodeFormats (영문)](https://love2d.org/wiki/EncodeFormat)로 디코딩합니다                                    |
| [encode (영문)](https://love2d.org/wiki/love.data.encode)               | Data 또는 문자열을 [EncodeFormats (영문)](https://love2d.org/wiki/EncodeFormat)로 인코딩합니다                                    |
| [hash (영문)](https://love2d.org/wiki/love.data.hash)                   | 지정된 해시 알고리즘을 사용하여 문자열의 다이제스트를 계산합니다                                                                     |
| [newDataView (영문)](https://love2d.org/wiki/love.data.newDataView)     | 기존 Data객체의 하위 섹션을 참조한 새 Data를 생성합니다                                                                            |
| [pack (영문)](https://love2d.org/wiki/love.data.pack)                   | 간단한 Lua 값을 패킹합니다(직렬화). 이 함수는 Lua 5.3 버전의 string.pack과 동일하게 동작합니다                                       |
| [unpack (영문)](https://love2d.org/wiki/love.data.unpack)               | 바이트-스트링 또는 Data를 언패킹(역직렬화)해서 간단한 Lua 값으로 바꿉니다. 이 함수는 Lua 5.3 버전의 string.unpack과 동일하게 동작합니다 |
| [getPackedSize (영문)](https://love2d.org/wiki/love.data.getPackedSize) | love.data.pack에 사용할 지정된 포맷 크기(바이트)를 가져옵니다. 이 기능은 Lua 5.3 버전의 string.packsize와 동일하게 동작합니다         |


<br>

## 타입

### Data

**_모든 data의 슈퍼클래스이며 평범하게 인스턴스화 할수 없습니다._**

| 이름       | 설명                                               |
|------------|---------------------------------------------------|
| clone      | Data 객체의 복사본을 만들고 반환합니다               |
| getPointer | Data 객체의 포인터를 반환합니다                     |
| getSize    | Data 객체의 크기를 바이트로 구합니다                 |
| getString  | Data 객체를 문자열로 구합니다                       |

<b><i>
이 함수들은 ByteData 또는 DataView 객체에 대해서도 적용됩니다.
</b></i>

더보기:
- [love.data.newDataView (영문)](https://love2d.org/wiki/love.data.newDataView)
- [love.data.newByteData (영문)](https://love2d.org/wiki/love.data.newByteData)