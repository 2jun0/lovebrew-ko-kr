# love.math

<b><i>
시스템에 독립적으로 작동하는 수학 함수를 제공합니다.
</b></i>

## 함수

| 이름                                                                                | 설명                                                          | 비고  |
|------------------------------------------------------------------------------------|---------------------------------------------------------------|-------|
| [isConvex](https://love2d.org/wiki/love.math.isConvex_(한국어))                     | 볼록한 다각형인지 여부를 구합니다                               |       |
| [newRandomGenerator](https://love2d.org/wiki/love.math.newRandomGenerator_(한국어)) | 새로운 난수 생성기를 생성합니다                                 |       |
| [newTransform (영문)](https://love2d.org/wiki/love.math.newTransform)               | Transform 객체를 생성합니다                                    |       |
| [gammaToLinear (영문)](https://love2d.org/wiki/love.math.gammaToLinear)             | 색깔 값을 감마 색 공간(sRGB)에서 선형 색 공간(RGB)으로 변환합니다 |       |
| [linearToGamma (영문)](https://love2d.org/wiki/love.math.linearToGamma)             | 색깔 값을 선형 색 공간(RGB)에서 감마 색 공간(sRGB)으로 변환합니다 |       |
| [triangulate (영문)](https://love2d.org/wiki/love.math.triangulate)                 | 단순 다각형을 삼각형으로 분해합니다                              |       |
| [colorToBytes (영문)](https://love2d.org/wiki/love.math.colorToBytes)               | 색깔 값을 0 ~ 1에서 0 ~ 255 범위 값으로 변환합니다               |       |
| [colorFromBytes (영문)](https://love2d.org/wiki/love.math.colorFromBytes)           | 색깔 값을 0 ~ 255에서 0 ~ 1 범위 값으로 변환합니다               |       |
| [random](https://love2d.org/wiki/love.math.random_(한국어))                         | 고르게 분포되어 있는 유사난수를 생성합니다                       |       |
| [randomNormal](https://love2d.org/wiki/love.math.randomNormal_(한국어))             | 정규 분포를 따르는 유사난수를 생성합니다                         |       |
| [getRandomState (영문)](https://love2d.org/wiki/love.math.getRandomState)           | 난수 생성기의 상태를 업어옵니다                                  |       |
| [getRandomSeed](https://love2d.org/wiki/love.math.getRandomSeed_(한국어))           | 난수 생성기의 시드를 얻어옵니다                                 |       |
| [setRandomSeed](https://love2d.org/wiki/love.math.setRandomSeed_(한국어))           | 난수 생성기의 시드를 설정합니다                                 |       |
| [setRandomState (영문)](https://love2d.org/wiki/love.math.setRandomState)           | 난수 생성기의 상태를 설정합니다                                  |       |

## Types

### RandomGenerator

<b><i>
자기 고유의 난수 상태를 가지는 난수 생성기입니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [love.math.newRandomGenerator](https://love2d.org/wiki/love.math.newRandomGenerator_(한국어))

| 이름                                                                          | 설명                                                | 비고  |
|-------------------------------------------------------------------------------|----------------------------------------------------|-------|
| [getSeed](https://love2d.org/wiki/RandomGenerator:getSeed_(한국어))           | 난수 생성기의 시드를 얻어옵니다                       |       |
| [getState (영문)](https://love2d.org/wiki/RandomGenerator:getState)           | 난수 생성기의 상태를 얻어옵니다                      |       |
| [randomNormal](https://love2d.org/wiki/RandomGenerator:randomNormal_(한국어)) | 정규 분포를 따르는 유사난수를 생성합니다               |       |
| [setSeed](https://love2d.org/wiki/RandomGenerator:setSeed_(한국어))           | 난수 생성기의 시드를 설정합니다                       |       |
| [setState (영문)](https://love2d.org/wiki/RandomGenerator:setState)           | 난수 생성기의 상태를 설정합니다                      |       |
| [random](https://love2d.org/wiki/RandomGenerator:random_(한국어))             | 고르게 분포되어 있는 유사난수를 생성합니다             |       |

### Transform

<b><i>
좌표계 변환이 포함되어 있는 객체입니다.<br>
love.graphics 모듈 함수에서 인자로 사용됩니다.
</b></i>

더보기:
- [Object](ko-kr/api/love?id=Object)
- [love.math.newTransform (영문)](https://love2d.org/wiki/love.math.newTransform)

| 이름                                                                                     | 설명                                                                                  | 비고  |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------|
| [clone (영문)](https://love2d.org/wiki/Transform:clone)                                 | Transform 객체를 복제합니다                                                             |       |
| [inverse (영문)](https://love2d.org/wiki/Transform:inverse)                             | 역 Transform 객체를 생성합니다                                                          |       |
| [apply (영문)](https://love2d.org/wiki/Transform:apply)                                 | 다른 Transform 객체를 이 객체에 적용합니다                                               |       |
| [isAffine2DTransform (영문)](https://love2d.org/wiki/Transform:isAffine2DTransform)     | Transform 객체가 아핀 변환(affine transformation)을 했는지 여부를 구합니다                |       |
| [translate (영문)](https://love2d.org/wiki/Transform:translate)                         | Transform 객체의 좌표계를 변환합니다                                                     |       |
| [rotate (영문)](https://love2d.org/wiki/Transform:rotate)                               | Transform 객체의 좌표계를 회전합니다                                                     |       |
| [scale (영문)](https://love2d.org/wiki/Transform:scale)                                 | Transform 객체의 좌표계의 크기를 조정합니다                                               |       |
| [shear (영문)](https://love2d.org/wiki/Transform:shear)                                 | Transform 객체의 좌표계에 전단 계수(skew)를 조정합니다                                    |       |
| [reset (영문)](https://love2d.org/wiki/Transform:reset)                                 | Transform 객체를 Identity Transform로 설정합니다.                                        |       |
| [setTransformation (영문)](https://love2d.org/wiki/Transform:setTransformation)         | 특정한 변환 파라미터로 재설정합니다                                                       |       |
| [setMatrix (영문)](https://love2d.org/wiki/Transform:setMatrix)                         | Transform 객체의 내부 변환행렬을 직접 설정합니다                                          |       |
| [getMatrix (영문)](https://love2d.org/wiki/Transform:getMatrix)                         | Transform 객체의 내수 변환행렬을 구합니다                                                 |       |
| [transformPoint (영문)](https://love2d.org/wiki/Transform:transformPoint)               | 주어진 2D 좌표에 Transform 객체의 변환을 적용합니다                                       |       |
| [inverseTransformPoint (영문)](https://love2d.org/wiki/Transform:inverseTransformPoint) | 주어진 2D 좌표에 Transform 객체의 역변환을 적용합니다                                      |       |