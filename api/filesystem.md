# love.filesystem

<b><i>
파일 입출력이나 폴더 관리에 필요한 함수를 제공합니다.

love.filesystem은 아래의 두 위치에만 접근하는 것을 허용합니다.

- .love 압축 파일(혹은 압축되지 않은 소스들이 있는 디렉터리)(읽기 전용)
- 세이브 디렉터리(읽기, 쓰기)

세이브 디렉터리는 파일을 저장할 수 있는 유일한 저장소입니다.<br>
각 게임마다 시스템 상에서 단 하나의 세이브 디렉터리를 가집니다. 시스템마다 다르긴 하겠지만 보통은 다음 디렉터리 안에 위치합니다.

- Windows XP: `C:\Documents and Settings\user\Application Data\LOVE\` 또는 `%appdata%\LOVE\`
- Windows Vista 또는 7: `C:\Users\user\AppData\Roaming\LOVE` 또는 `%appdata%\LOVE\`
- Linux: `$XDG_DATA_HOME/love/` 또는 `~/.local/share/love/`
- Mac: `/Users/user/Library/Application Support/LOVE/`
쓰기 모드로 열린 파일은 쓸 수 있는 저장소가 하나밖에 없으니 저장시 루트를 세이브 디렉터리로 해서 생성됩니다.

읽기 모드로 열린 파일은 세이브 디렉터리와 .love 압축 파일 두 군데에 동시에 접근할 수 있습니다. 여기서 한 가지 문제점이 발생하는데, love.filesystem은 이 두 위치를 모두 루트로 취급한다는 것입니다. 따라서 만약 동일한 이름과 경로를 가진 파일이 .love 압축 파일과 세이브 디렉터리 둘 다 존재할 경우, 세이브 디렉터리에 있는 파일을 우선적으로 접근하게 됩니다.

정리하자면, 모든 경로는 .love 압축 파일과 세이브 디렉터리가 루트 디렉터리로 간주되어진 경로입니다. (get*Directory()를 통한 접근 제외)

`[conf.lua](https://love2d.org/wiki/Config_Files_(한국어))`에서 세이브 디렉터리의 이름을 정해보세요. `[love.filesystem.setIdentity](https://love2d.org/wiki/love.filesystem.setIdentity_(한국어))`에서 설정할 수도 있습니다.

</b></i>

?> 스탠다드 `io` 라이브러리로도 SD 카드에 있는 파일을 접근할 수 있습니다.

## 함수

| 이름                                                                                              | 설명                                                                                  | 비고  |
|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-------|
| [init](https://love2d.org/wiki/love.filesystem.init_(한국어))                                     | love.filesystem을 초기화합니다. 내부적으로 사용되는 함수이므로 함부로 호출하지 마세요      |       |
| [append](https://love2d.org/wiki/love.filesystem.append_(한국어))                                 | 이미 존재하는 파일에 데이터를 추가합니다                                                 |       |
| [createDirectory](https://love2d.org/wiki/love.filesystem.createDirectory_(한국어))               | 디렉토리를 생성합니다                                                                  |       |
| [getDirectoryItems](https://love2d.org/wiki/love.filesystem.getDirectoryItems_(한국어))           | 특정 디렉토리 내에 있는 모든 파일과 하위 디렉토리를 나열한 테이블을 반환합니다              |       |
| [getIdentity](https://love2d.org/wiki/love.filesystem.getIdentity_(한국어))                       | 게임에서 사용하고 있는 세이브 디렉토리의 이름을 구합니다                                  |       |
| [getInfo (영문)](https://love2d.org/wiki/love.filesystem.getInfo)                                 | 특정한 파일이나 디렉터리의 정보를 구합니다                                               |       |
| [getRealDirectory (영문)](https://love2d.org/wiki/love.filesystem.getRealDirectory)               | 파일 경로를 포함한 디렉터리의 절대경로를 구합니다                                        |       |
| [getRequirePath (영문)](https://love2d.org/wiki/love.filesystem.getRequirePath)                   | 요구가 호출될 때 검색할 파일 시스템의 경로를 구합니다                                     |       |
| [getSaveDirectory](https://love2d.org/wiki/love.filesystem.getSaveDirectory_(한국어))             | 세이브 디렉토리의 완전한 경로를 구합니다                                                 |       |
| [getSourceBaseDirectory (영문)](https://love2d.org/wiki/love.filesystem.getSourceBaseDirectory)   | .love 파일을 포함한 디렉터리의 전체 경로를 반환합니다                                    |       |
| [getSource (영문)](https://love2d.org/wiki/love.filesystem.getSource)                             | .love 파일이나 디렉터리의 전체 경로를 반환합니다                                         |       |
| [getUserDirectory](https://love2d.org/wiki/love.filesystem.getUserDirectory_(한국어))             | 사용자 디렉토리를 받아옵니다                                                            |       |
| [getWorkingDirectory](https://love2d.org/wiki/love.filesystem.getWorkingDirectory_(한국어))       | 현재 작업 디렉토리를 받아옵니다                                                         |       |
| [isFused](https://love2d.org/wiki/love.filesystem.isFused_(한국어))                               | 게임이 퓨즈 모드로 설정되어 있는지 조사합니다                                            |       |
| [lines](https://love2d.org/wiki/love.filesystem.lines_(한국어))                                   | 텍스트 파일을 한 줄씩 읽는 반복자를 반환합니다                                           |       |
| [load](https://love2d.org/wiki/love.filesystem.load_(한국어))                                     | Lua 파일을 불러오기만 합니다. 불러옴과 동시에 실행하지는 않습니다                          |       |
| [mount](https://love2d.org/wiki/love.filesystem.mount_(한국어))                                   | 게임의 저장 디렉티리내 zip파일 및 폴더를 마운트 합니다                                    |       |
| [newFile](https://love2d.org/wiki/love.filesystem.newFile_(한국어))                               | 새 파일 객체를 생성합니다                                                               |       |
| [newFileData](https://love2d.org/wiki/love.filesystem.newFileData_(한국어))                       | 새 FileData 객체를 생성합니다                                                          |       |
| [read](https://love2d.org/wiki/love.filesystem.read_(한국어))                                     | 파일의 내용을 읽습니다                                                                  |       |
| [remove](https://love2d.org/wiki/love.filesystem.remove_(한국어))                                 | 파일 또는 디렉토리를 제거합니다                                                         |       |
| [setIdentity](https://love2d.org/wiki/love.filesystem.setIdentity_(한국어))                       | 게임에서 사용할 세이브 디렉토리의 이름을 정합니다                                         |       |
| [setRequirePath (영문)](https://love2d.org/wiki/love.filesystem.setRequirePath)                   | 요구가 호출될때 검색할 파일 시스템 경로를 설정합니다                                      |       |
| [setSource](https://love2d.org/wiki/love.filesystem.setSource_(한국어))                           | 내부적으로 사용할 소스 코드가 있는 위치를 설정합니다                                      |       |
| [unmount](https://love2d.org/wiki/love.filesystem.unmount_(한국어))                               | love.filesystem.mount로 마운트된 zip 파일 또는 폴더를 언마운트 합니다                    |       |
| [write](https://love2d.org/wiki/love.filesystem.write_(한국어))                                   | 파일에 데이터를 씁니다                                                                  |       |

## 타입

### File

<b><i>
파일 시스템 위에서 동작하는 파일을 표현합니다.
</b></i>

더보기:
- [love.filesystem.newFile](https://love2d.org/wiki/love.filesystem.newFile_(한국어))
- [Object](ko-kr/api/love?id=Object)

| 이름                                                          | 설명                                            | 비고                                                        |
|--------------------------------------------------------------|-------------------------------------------------|-------------------------------------------------------------|
| [close](https://love2d.org/wiki/File:close_(한국어))          | 파일을 닫습니다                                  |                                                             |
| [flush](https://love2d.org/wiki/File:flush_(한국어))          | 버퍼를 완전히 비웁니다                            |                                                             |
| [getBuffer](https://love2d.org/wiki/File:getBuffer_(한국어))  | 버퍼링 모드를 얻어옵니다                          |                                                             |
| [getFilename (영문)](https://love2d.org/wiki/File:getFilename)| 파일 이름을 구합니다                              |                                                             |
| [getMode](https://love2d.org/wiki/File:getMode_(한국어))      | 파일 모드를 얻어옵니다                            |                                                             |
| [getSize](https://love2d.org/wiki/File:getSize_(한국어))      | 파일의 크기를 구합니다                            |                                                             |
| [isEOF (영문)](https://love2d.org/wiki/(File):isEOF)          | 파일의 끝에 도달하면 true를 반환합니다             | [eof](https://love2d.org/wiki/File:eof_(한국어))를 참고하세요 |
| [isOpen](https://love2d.org/wiki/File:isOpen_(한국어))        | 파일이 열려 있는지 확인합니다                      |                                                             |
| [lines](https://love2d.org/wiki/File:lines_(한국어))          | 텍스트 파일을 한 줄씩 읽는 반복자를 반환합니다      |                                                             |
| [open](https://love2d.org/wiki/File:open_(한국어))            | 읽기나 쓰기 따위를 하기 위해 파일을 엽니다          |                                                             |
| [read](https://love2d.org/wiki/File:read_(한국어))            | 파일을 읽습니다                                   |                                                             |
| [seek](https://love2d.org/wiki/File:seek_(한국어))            | 파일의 포인터 위치를 변경합니다                    |                                                             |
| [setBuffer (영문)](https://love2d.org/wiki/File:setBuffer)    | 파일 쓰기와 추가 시 사용할 버퍼링 모드를 설정합니다 |                                                             |
| [tell (영문)](https://love2d.org/wiki/File:tell)              | 파일의 포인터 위치를 반환합니다                    |                                                             |
| [write](https://love2d.org/wiki/File:write_(한국어))          | 데이터를 파일에 씁니다                            |                                                             |


### FileData

<b><i>
파일 내부의 콘텐츠를 가리키는 데이터 입니다.
</b></i>

더보기:
- [love.filesystem.newFileData](https://love2d.org/wiki/love.filesystem.newFileData_(한국어))
- [Data](ko-kr/api/data)
- [Object](ko-kr/api/love?id=Object)

| 이름                                                                   | 설명                                   | 비고  |
|------------------------------------------------------------------------|---------------------------------------|-------|
| [clone (영문)](https://love2d.org/wiki/FileData:clone)                 | FileData 객체를 복제합니다              |       |
| [getFilename (영문)](https://love2d.org/wiki/FileData:getFilename)     | FileData 객체의 이름을 구합니다         |       |
| [getExtension](https://love2d.org/wiki/FileData:getExtension_(한국어)) | FileData 객체의 확장자를 구합니다        |       |