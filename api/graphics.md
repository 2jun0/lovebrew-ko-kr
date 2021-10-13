# love.graphics

<b><i>
love.graphics 모듈의 가장 기본적인 역할은 선과 도형, 텍스트, 이미지, 그리고 여러 Drawable 객체를 화면에 출력하는 것입니다. 그 외에 외부 파일(이미지, 글꼴)을 메모리로 불러오거나 특정한 객체를 생성(ParticleSystem, Canvas)하며, 좌표 평면을 관리하기도 합니다.

LÖVE는 좌상단 우선 좌표계를 사용합니다. x축은 수평이며, 값이 점점 커질수록 오른쪽으로 이동합니다. y축은 수직이고, 값이 증가할수록 밑으로 움직입니다.
</b></i>

## 함수

| 이름                                                                                        | 설명                                                                                                                                   | 비고                                                                             |
|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| [arc (영문)](https://love2d.org/wiki/love.graphics.arc)                                     | 원 곡선을 그립니다                                                                                                       |                                                                                  |    
| [applyTransform (영문)](https://love2d.org/wiki/love.graphics.applyTransform)               | 주어진 Transform 객체에 대해 현재 좌표계를 적용합니다                                        |                                                                                  |
| [circle (영문)](https://love2d.org/wiki/love.graphics.circle)                               | 원을 그립니다                                                                                                     |                                                                                  |
| [clear (영문)](https://love2d.org/wiki/love.graphics.clear)                                 | 스크린이나 활성화된 캔버스를 특정한 색으로 지웁니다                                                          |                                                                                  |  
| [draw (영문)](https://love2d.org/wiki/love.graphics.draw)                                   | 스크린에 물체를 그립니다                                                                                            |                                                                                  | 
| [ellipse (영문)](https://love2d.org/wiki/love.graphics.ellipse)                             | 타원을 그립니다                                                                                                   |                                                                                  |
| getActiveScreen                                                                             | 랜더링 중인 스크린을 구합니다                                                                                |                                                                                  |
| [getBackgroundColor (영문)](https://love2d.org/wiki/love.graphics.getBackgroundColor)       | 현재 배경 색을 구합니다                                                                                  |                                                                                  |
| getBlendFactor                                                                              | 블랜딩 요소[0 - 1]를 구합니다                                                                                                           | 닌텐도 3DS 한정                                                                   |
| [getColor (영문)](https://love2d.org/wiki/love.graphics.getColor)                           | 색깔 값을 구합니다                                                                                             |                                                                                  |
| [getDefaultFilter (영문)](https://love2d.org/wiki/love.graphics.getDefaultFilter)           | 이미지, 캔버스, 폰트의 디폴트 크기필터를 반환합니다                                          |                                                                                  |
| [getDimensions (영문)](https://love2d.org/wiki/love.graphics.getDimensions)                 | 창의 너비와 높이를 구합니다                                                                                                              | 3DS에선, 특정 스크린의 크기를 구하려면 "top" 또는 "bottom"를 인자로 넘겨야 합니다.    |
| [getFont (영문)](https://love2d.org/wiki/love.graphics.getFont)                             | 현재 설정된 글꼴 객체를 가져옵니다                                                                                 |                                                                                  |
| [getHeight (영문)](https://love2d.org/wiki/love.graphics.getHeight)                         | 창의 높이를 픽셀로 구합니다                                                                            |                                                                                  |
| [getLineWidth (영문)](https://love2d.org/wiki/love.graphics.getLineWidth)                   | 선의 길이를 구합니다                                                                                        |                                                                                  |
| [getPointSize (영문)](https://love2d.org/wiki/love.graphics.getPointSize)                   | 점의 크기를 구합니다                                                                                        |                                                                                  |
| get3DDepth                                                                                  | 3DS에서 3D 슬라이더 값을 구합니다 (0 ~ 1), 3D 랜더링에 유용합니다                                                                          | 스위치에선 오류가 발생합니다                                                        |
| [getRendererInfo (영문)](https://love2d.org/wiki/love.graphics.getRendererInfo)             | 시스템의 비디오 카드와 드라이버의 정보를 구합니다                                                         |                                                                                  |
| [getScissor (영문)](https://love2d.org/wiki/love.graphics.getScissor)                       | 잘라내기 지정 영역를 가져옵니다                                                                                       |                                                                                  |
| getScreens                                                                                  | 랜더링 가능한 스크린 이름을 가져옵니다                                                                            |                                                                                  |
| get3D                                                                                       | 입체 3D 활성 여부를 확입합니다                                                                                |                                                                                  |
| [getWidth (영문)](https://love2d.org/wiki/love.graphics.getWidth)                           | 창의 너비를 픽셀로 구합니다                                                                                                              | 3DS에선, 특정 스크린의 너비를 구하려면 "top" 또는 "bottom"를 인자로 넘겨야 합니다.    |
| [instersectScissor (영문)](https://love2d.org/wiki/love.graphics.instersectScissor)         | 지정된 직사각형과 기존 지정 영역가 교차하여 만들어진 직사각형으로 새 지정 영역를 설정합니다 |                                                                                  |
| [inverseTransformPoint (영문)](https://love2d.org/wiki/love.graphics.inverseTransformPoint) | 스크린 공간의 2D 좌표를 전역 좌표로 변환합니다                                           |                                                                                  |
| [line (영문)](https://love2d.org/wiki/love.graphics.line)                                   | 점들을 잇는 선을 그립니다                                                                                         |                                                                                  |
| [newCanvas (영문)](https://love2d.org/wiki/love.graphics.newCanvas)                         | 새 캔버스를 생성합니다                                                                                               |                                                                                  |
| [newFont (영문)](https://love2d.org/wiki/love.graphics.newFont)                             | 새 글꼴을 생성합니다                                                                                                                    | 3DS: 글꼴을 bcfnt로 변환, 스위치: 트루타입만 가능                                   |
| [newImage (영문)](https://love2d.org/wiki/love.graphics.newImage)                           | 새 이미지를 생성합니다                                                                                                                   | 3DS: 이미지를 t3x로 변환, 스위치: png 또는 jpg을 지원함                             |
| [newText (영문)](https://love2d.org/wiki/love.graphics.newText)                             | 그릴 수 있는 텍스트 개체를 생성합니다                                                                                 |                                                                                  |
| [newQuad (영문)](https://love2d.org/wiki/love.graphics.newQuad)                             | 새 사각형을 생성합니다                                                                                                |                                                                                  |
| [origin (영문)](https://love2d.org/wiki/love.graphics.origin)                               | 현재 좌표 변환을 초기화 합니다                                                                       |                                                                                  |
| [polygon (영문)](https://love2d.org/wiki/love.graphics.polygon)                             | 다각형을 그립니다                                                                                                     |                                                                                  |
| [pop (영문)](https://love2d.org/wiki/love.graphics.pop)                                     | 변환 스택에서 좌표 변환을 pop합니다                                           |                                                                                  |
| [points (영문)](https://love2d.org/wiki/love.graphics.points)                               | 하나 혹은 여러개의 점을 그립니다                                                                                                         | 3DS에선 아직 구현되지 않았음                                                       |
| [present (영문)](https://love2d.org/wiki/love.graphics.present)                             | 드로잉 결과를 스크린에 보여줍니다                                                           |                                                                                  |
| [print (영문)](https://love2d.org/wiki/love.graphics.print)                                 | 스크린에 텍스트를 그립니다. 폰트가 설정되지 않았다면 필요에 따라 글꼴이 생성되고 설정됩니다.(한번만)                              |                                                                                  |
| [printf (영문)](https://love2d.org/wiki/love.graphics.printf)                               | 줄 바꿈 및 정렬을 사용하여 서식 있는 텍스트를 그립니다                                                                                     | LÖVE와 스위치는 문자열 래핑, 3DS는 문자 래핑                                        |
| [push (영문)](https://love2d.org/wiki/love.graphics.push)                                   | 변환 스텍에 좌표 변환을 복사 후 push합니다                                |                                                                                  |
| [rectangle (영문)](https://love2d.org/wiki/love.graphics.rectangle)                         | 직사각형을 그립니다                                                                                                  |                                                                                  |
| [replaceTransform (영문)](https://love2d.org/wiki/love.graphics.replaceTransform)           | 좌표 변환을 주어진 Transform 객체로 교체합니다                                     |                                                                                  |
| [reset (영문)](https://love2d.org/wiki/love.graphics.reset)                                 | 현재 그래픽 설정을 초기화 합니다                                                                               |                                                                                  |
| [rotate (영문)](https://love2d.org/wiki/love.graphics.rotate)                               | 2차원에서 좌표계를 회전합니다                                                                    |                                                                                  |
| [scale (영문)](https://love2d.org/wiki/love.graphics.scale)                                 | 2차원에서 좌표계의 크기를 조절합니다                                                                     |                                                                                  |
| [shear (영문)](https://love2d.org/wiki/love.graphics.shear)                                 | 좌표계를 전단변환 합니다                                                                                       |                                                                                  |
| setActiveScreen                                                                             | 렌더링될 스크린을 설정합니다                                                                                                             | 내부적으로만 사용되니 호출하지 말것                                                 |
| [setBackgroundColor (영문)](https://love2d.org/wiki/love.graphics.setBackgroundColor)       | 배경색을 설정합니다                                                                                          |                                                                                  |
| setBlendFactor                                                                              | 블랜딩 요소[0 - 1]를 설정합니다. 닌텐도 3DS 한정                                                                                         | num >= 0 이면 이미지에 틴트 효과를 부여하고 0이면 부여하지 않습니다.                  |
| set3D                                                                                       | 입체 3D의 활성화 여부를 설정합니다. 닌텐도 3DS 한정                                                         |                                                                                  |
| [setCanvas (영문)](https://love2d.org/wiki/love.graphics.setCanvas)                         | 드로잉 작업을 캔버스로 캡쳐합니다                                                                            |                                                                                  |
| [setColor (영문)](https://love2d.org/wiki/love.graphics.setColor)                           | 그리기에 사용되는 색을 설정합니다                                                                                                         | 3DS에선, 제한으로 인해 알파 색상값만 텍스쳐에 영향을 줍니다                           |
| [setDefaultFilter (영문)](https://love2d.org/wiki/love.graphics.setDefaultFilter)           | 이미지, 캔버스, 글꼴에 사용되는 디폴트 스케일링 필터를 설정합니다                                             |                                                                                  |
| [setLineWidth (영문)](https://love2d.org/wiki/love.graphics.setLineWidth)                   | 선의 길이를 설정합니다                                                                                                |                                                                                  |
| [setNewFont (영문)](https://love2d.org/wiki/love.graphics.setNewFont)                       | 글꼴을 생성하고 설정합니다                                                                                        |                                                                                  |
| [setPointSize (영문)](https://love2d.org/wiki/love.graphics.setPointSize)                   | 점의 크기를 설정합니다                                                                                                |                                                                                  |
| [setFont (영문)](https://love2d.org/wiki/love.graphics.setFont)                             | 로딩된 폰트를 현재 지정 영역에 적용합니다                                                                     |                                                                                  |
| [setScissor (영문)](https://love2d.org/wiki/love.graphics.setScissor)                       | 지정 영역을 설정하거나 취소합니다                                                                                           |                                                                                  |
| [transformPoint (영문)](https://love2d.org/wiki/love.graphics.transformPoint)               | 주어진 2D 좌표를 전역좌표에서 스크린-영역 좌표로 변환합니다                                           |                                                                                  |
| [translate (영문)](https://love2d.org/wiki/love.graphics.translate)                         | 좌표계를 2차원으로 변환합니다

## 타입

### Texture

<b><i>
텍스쳐를 나타내는 그리기 가능한 객체에 대한 슈퍼 클래스입니다.<br>
모든 텍스쳐는 사각형으로 그려집니다.
</b></i>

더보기:
* [Object](ko-kr/api/love?id=Object)

| 이름                                                                    | 설명                                       | 비고  |
|-------------------------------------------------------------------------|-------------------------------------------|-------|
| [getTextureType (영문)](https://love2d.org/wiki/Texture:getTextureType) | 텍스쳐의 타입을 구합니다                     |       |
| [getWidth (영문)](https://love2d.org/wiki/Texture:getWidth)             | 텍스쳐의 너비를 구합니다                     |       |
| [getHeight (영문)](https://love2d.org/wiki/Texture:getHeight)           | 텍스쳐의 높이를 구합니다                     |       |
| [getDimensions (영문)](https://love2d.org/wiki/Texture:getDimensions)   | 텍스쳐의 너비와 높이를 구합니다              |       |
| [setFilter (영문)](https://love2d.org/wiki/Texture:setFilter)           | 텍스쳐의 필터 모드를 설정합니다              |       |
| [getFilter (영문)](https://love2d.org/wiki/Texture:getFilter)           | 텍스쳐의 필터 모드를 구합니다                |       |
| [setWrap (영문)](https://love2d.org/wiki/Texture:setWrap)               | 텍스쳐의 래핑 속성을 설정합니다              |       |
| [getWrap (영문)](https://love2d.org/wiki/Texture:getWrap)               | 텍스쳐의 래핑 속성을 구합니다                |       |

### Canvas

<b><i>
캔버스는 화면 밖의 렌더링에 사용됩니다.<br>
실제 보이는 화면에 그리기 전에 그리는 보이지 않는 화면이라고 생각하세요.<br>
이 방식을 "텍스쳐를 렌더링한다" 라고 합니다.<br>
이렇게 하는 이유는 성능 때문인데, 위치가 자주 변경되지 않는 것(예: 배경) 등을 캔버스로 그린 뒤, 캔버스 단위로 그리면 그리기 작업 수를 줄일 수 있기 때문입니다.
</b></i>

더보기:
* [Texture](#texture)
* [Object](ko-kr/api/love?id=Object)
* [love.graphics.newCanvas (영문)](https://love2d.org/wiki/love.graphics.newCanvas)

| 이름                                                       | 설명                                | 비고  |
|-----------------------------------------------------------|-------------------------------------|-------|
| [renderTo (영문)](https://love2d.org/wiki/Canvas:renderTo) | 함수를 이용해서 캔버스에 렌더링 합니다 |       |

### Image

<b><i>
그릴 수 있는 이미지 타입입니다.
</b></i>

!> 3DS에서 이미지는 `*.t3x` 포맷으로 변환되어야 합니다. [호환성](ko-kr/compatibility?id=그리기)항목을 참조하세요.

더보기:
* [Texture](#texture)
* [Object](ko-kr/api/love?id=Object)
* [love.graphics.newImage (영문)](https://love2d.org/wiki/love.graphics.newImage)

### Quad

<b><i>
텍스처 좌표 정보가 있는 사각형(변과 모서리가 4개인 폴리곤)입니다.<br>
쿼드를 사용하여 그릴 텍스처의 일부를 선택할때 사용됩니다. 이러한 방식으로 하나의 큰 텍스처 지도를 로드한 다음, 하위 이미지로 분할할 수 있습니다.
</b></i>

더보기:
* [Object](ko-kr/api/love?id=Object)
* [love.graphics.newQuad (영문)](https://love2d.org/wiki/love.graphics.newQuad)

| 이름                                                                             | 설명                                                                    | 비고  |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------|-------|
| [getTextureDimensions (영문)](https://love2d.org/wiki/Quad:getTextureDimensions) | love.graphics.newQuad에 처음 지정된 참조 텍스쳐 면적을 가져옵니다          |       |
| [getViewport (영문)](https://love2d.org/wiki/Quad:getViewport)                   | 쿼드의 현재 뷰포트를 가져옵니다                                           |       |
| [setViewport (영문)](https://love2d.org/wiki/Quad:setViewport)                   | 뷰포트에 따른 텍스쳐 좌표를 설정합니다                                     |       |

!> 닌텐도 3DS에선, `love.graphics.print`을 통한 텍스트와 글꼴 객체는 한번에 인쇄할 수 있는 글자가 512자로 제한됩니다. 이는 콘솔 기기의 엄격한 규정 때문입니다. 또, 시스템 폰트는 탭 문자(`\t`)가 없으며  System fonts `[?]` 글리프로 랜더링 됩니다.

### Font

<b><i>
글꼴 객체.<br>
스크린위에 그려질 문자의 형상을 정의합니다.
</b></i>

!> 3DS에선 글꼴을 사용하기 전에 `*.bcfnt` 포맷으로 변환해야 합니다. [호환성](ko-kr/compatibility?id=시스템 글꼴 불러오기)항목을 참고하세요.

더보기:
* [Object](ko-kr/api/love?id=Object)
* [love.graphics.newFont (영문)](https://love2d.org/wiki/love.graphics.newFont)

| 이름                                                       | 설명                            | 비고  |
|------------------------------------------------------------|--------------------------------|-------|
| [getHeight (영문)](https://love2d.org/wiki/Font:getHeight) | 글꼴의 높이를 픽셀로 가져옵니다   |       |
| [getWidth (영문)](https://love2d.org/wiki/Font:getWidth)   | 글꼴의 너비를 픽셀로 가져옵니다   |       |

### Text

<b></i>
그리기 가능한 텍스트 객체
</b></i>

더보기:
* [Object](ko-kr/api/love?id=Object)
* [love.graphics.newText (영문)](https://love2d.org/wiki/love.graphics.newText)

| 이름                                                               | 설명                                                    | 비고                                                                           |
|-------------------------------------------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------------|
| [add (영문)](https://love2d.org/wiki/Text:add)                     | 특정한 위치의 텍스트 객체에 색칠된 텍스트를 추가합니다      |                                                                                |
| [addf (영문)](https://love2d.org/wiki/Text:addf)                   | 특정한 위치의 텍스트 객체에 포맷/색칠된 텍스트를 추가합니다 | 3DS에선 텍스트를 추가할 수 있지만, 다중 랩 및 정렬 모드를 허용하지 않습니다          |
| [clear (영문)](https://love2d.org/wiki/Text:clear)                 | 텍스트 객체의 내용을 제거합니다                           |                                                                                |
| [getDimensions (영문)](https://love2d.org/wiki/Text:getDimensions) | 텍스트의 높이와 너비를 구합니다                           |                                                                                |
| [getFont (영문)](https://love2d.org/wiki/Text:getFont)             | 텍스트 객체의 글꼴을 구합니다                             |                                                                                |
| [getHeight (영문)](https://love2d.org/wiki/Text:getHeight)         | 텍스트의 높이를 구합니다                                  |                                                                                |
| [getWidth (영문)](https://love2d.org/wiki/Text:getWidth)           | 텍스트의 너비를 구합니다                                  |                                                                                |
| [set (영문)](https://love2d.org/wiki/Text:set)                     | 텍스트 객체의 내용을 새로운 문자열로 교체합니다             |                                                                                |
| [setf (영문)](https://love2d.org/wiki/Text:setf)                   | 텍스트 객체의 내용을 새롭게 포맷된 문자열로 교체합니다      |                                                                                |
| [setFont (영문)](https://love2d.org/wiki/Text:setFont)             | 텍스트의 글꼴을 교체합니다                                |                                                                                |
