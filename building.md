?> 아래의 내용은 중요한 정보이니 꼼꼼하게 보셔야 합니다. 또한 필요하다면 다른 링크를 타고 더 자세히 읽어보십시오.

## 시작하기

시작하기 전에 [the instructions on the devkitPro wiki (영문)](https://devkitpro.org/wiki/Getting_Started)를 따라 개발환경을 설정하세요.

### 의존성

개발환경이 설정되면 터미널을 열고 아래와 같이 패키지 목록을 동기화합니다.

<!-- tabs:start -->
#### **Windows (msys2)**
```bash
pacman -Syu
```
#### **Unix-like (Linux, macOS)**
```bash
sudo (dkp-)pacman -Syu
```
<!-- tabs:end -->

패키지 목록이 동기화되면 다음을 실행합니다.

<!-- tabs:start -->
#### **Windows (msys2)**
```bash
pacman -S switch-dev 3ds-dev
```
#### **Unix-like (Linux, macOS)**
```bash
sudo (dkp-)pacman -S switch-dev 3ds-dev devkit-env
```
<!-- tabs:end -->

!> 다음 정보는 개발 목적으로만 제공됩니다! 프로그래밍을 이해하지 못하거나 기여하지 않을 경우 LÖVE Potion을 직접 빌드하지 마십시오. 이는 [비표준화 문제 (영문)](https://en.wikipedia.org/wiki/Market_fragmentation))를 야기할 수 있습니다. 배포용 게임을 패키징하려면 [게임 배포](ko-kr/packaging)를 참조하십시오.

그런 다음 저장소를 복제합니다. 코드를 기여하는 경우 [fork한 후 로컬로 복제하세요 (영문)](https://help.github.com/articles/fork-a-repo/). 이후, 터미널에서 복제된 LÖVE Potion 디렉터리로 이동합니다.

```bash
cd LovePotion
```

필요한 portlibs를 아래와 같이 설치합니다.

<!-- tabs:start -->

#### **Windows (msys2)**
```bash
pacman -S --needed - < pkglist.txt
```

#### **Unix-like (Linux, macOS)**
```bash
sudo (dkp-)pacman -S --needed - < pkglist.txt
```
<!-- tabs:end -->

모든 설치가 완료되면 make를 실행합니다. `make -j{CPU_CORES}`를 통해 할당할 작업을 더 지정할 수 있습니다. 여기서 {CPU_CORES}는 당신 CPU의 프로세서 코어 개수입니다. MAX_CORES - 1 을 사용하는 것이 좋습니다.

## Pull Requests

### 네이밍

새로운 [pull request (영문)](https://help.github.com/articles/about-pull-requests/)를 제출할 때, `fix-filesystem-reading`과 같이 쉽게 이해할 수 있는 네이밍을 해주세요. 이렇게 하면 향후 커밋에서 병합(승인 후)될 때 생길 수 있는 [결점을 추적하는](https://sqa.stackexchange.com/a/20258) 데 도움이 됩니다.

### 중괄호 스타일

일관성을 위해 중괄호({})는 항상 [Allman 스타일](https://pbs.twimg.com/media/CXlB_kpVAAA0pDM.png)이어야 합니다. 단, 구문이 한 줄인 경우는 중괄호를 생략하세요.

```cpp
if (something)
    printf("Woah!");
else if (otherThing)
    printf("Amazing!");
else
    printf("Welp");

for (size_t i = 0; i < 10; i++)
    printf("Count is %zu", i);
```

### 변수 & 함수 이름

- 변수 이름은 카멜 케이스(camelCase)로 지어야 합니다.
- 클래스 이름은 타이틀 케이스(Titlecase)로 지어야 합니다.
    - 함수 이름은 카멜 케이스(camelCase)로 지어야 합니다.
- Lua 래퍼함수는 클래스 함수 이름처럼 되야 합니다.
