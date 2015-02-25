---
layout: post
comments: true
title: Youtube 반응형 동영상 삽입 그외 iframe
date: 2015-01-15 12:27:06.000000000 -05:00
categories:
- BROWSER
- CSS
- HTML
- tip
thumbnail: 2015youtubee.jpeg
---
[Youtube](http://youtube.com), [Vimeo](http://vimeo.com) 같은 동영상들을 반응형 레이아웃및 디자인에 삽입하는 기법이다.  Responsive 반응형 틀을 만들고 그 틀에 `iframe`, `embed`를 맞추는 방법인데 상당히 쉽다.  [Thierry Koblenz](http://alistapart.com/article/creating-intrinsic-ratios-for-video/)가 내 놓았던 기법으로 알려져 있지만 뭐 이곳저곳에 널리 퍼져있는지라 쉽게 접할수 있는 기법이라 생각된다.

여담으로 다들 아실꺼라 생각하며 지나가던 것들이 너무나도 많은데 시간이 흐르고 보니 그래도 적어 놓는것이 나중에 돌아보게 되고 찾기도 쉽게 되던듯 하여 안그래도 많이하는 키보드놀이를 블로그에까지 다시 확장하려 한다.

Youtube 의 동영상을 외부에 삽입할 시에 제공되는 코드는 `iframe`으로 아주 오래오래 묵혀온 방법이다. Vimeo 도 마찬가지 이고.  `width`, `height`이 패키지로 흘러나오는 `iframe`은 달갑지만은 않다. 

```html
<iframe width="560" height="315" src="//www.youtube.com/embed/c_m2F_ph_uU" frameborder="0" allowfullscreen>
</iframe>
```

유튭에서 제공하는 복사코드.

## 반응형 유튜브 비디오

기본적인 컨셉은 해당 `iframe`을 `div`로 감싸는것이다. 그리고 그 감싼 `div`에 `padding` 값을 지정하는것이 키가 되겠다.

1. 첫째로 `iframe` 을 `div`로 감싸고,

    ```html
    <div>  
      <iframe width="560" height="315" src="//www.youtube.com/embed/c_m2F_ph_uU" frameborder="0" allowfullscreen></iframe>
    </div>
    ```

2. 둘째로 감싼 `div`에 중요한 `padding` 및 `height`지정등을 한다.

    ```css
    div {
      position: relative;
      padding-bottom: 56.25%;
      padding-top: 35px;
      height: 0;
      overflow: hidden;
    }
    ```
    `position: relative;` 를 지정해서 후에 `iframe`이 `position:absolute;` 을 가능토록 하는 것이고
    `padding-bottom: 56.25%;` 는 16:9 비율의 비디오틀을 잡아준다.  아마 가장 중요하지 않을까 싶다.
    그에 따라서 `height: 0;` 으로 잡아줘야 하고
    `padding-top:35px;` 은 Chrome의 Youtube비디오를 위한 공간을 만들어 주는 것이다.

3. 마지막으로 `div`안의 `iframe`을 `div`에 맞추도록 스타일을 입힌다.

    ```css
    div iframe {
        position: absolute;
        top:0;
        left: 0;
        width: 100%;
        height: 100%;
    }
    ```

    위에서 언급했듯이 `absolute` 포지션을 잡아주고 `top`과 `left`값을 `0`으로 지정후에 너비와 높이를 `100%;` 로 지정한다. Embed와 object 들도 이렇게 적용 시키면 되겠다.

아시다시피 위의 아이디어는 가장 기본적인 반응형 동영상 삽입을 위한 `iframe` 을 조작하는 방법이다.  이 컨셉을 바탕으로 `js`를 사용할수도 있겠고 활용도는 무궁무진하다.
이 컨셉을 그냥 그대로 포스트에 삽입하고 싶다면 삽입코드를 제공하는 [embedresponsively.com](http://embedresponsively.com) 과 같은 사이트를 활용 할 수도 있고 간편하게 [js 플러그인](http://gomakethings.com/using-fluidvids-js/)도 있다.

참고로 IE구형버전에는 `div`를 한번 더 입히는걸 추천하고 있다.
정리된 `embed` 의 `html` 코드.

```html
<div id="containingBlock">
  ...

<div class="videoWrapper wideScreen chrome_25">
<div>
      <object width="480" height="295"><param name="movie" value="http://www.youtube.com/v/mDRYnaajUcY&hl=en&fs=1" /><param name="allowFullScreen" value="true" /><param name="allowscriptaccess" value="always" /><embed src="http://www.youtube.com/v/mDRYnaajUcY&hl=en&fs=1" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="480" height="295"></embed></object>
    </div>

</div>
  ...      

<div class="videoWrapper fourBYthree chrome_35">
<div>
      <embed src="http://d.yimg.com/cosmos.bcst.yahoo.com/up/fop/embedflv/swf/fop.swf?shareEnable=1&id=11795504&autoStart=0&infoEnable=0&shareEnable=0&prepanelEnable=1&carouselEnable=0&postpanelEnable=1" width="400" height="300" type="application/x-shockwave-flash"></embed></div>

</div>
  ...

</div>
```

그리고 정리된 css

```css
#containingBlock {width:50%;}
.videoWrapper {
  position:relative;
  height: 0;
}
* html .videoWrapper {
  margin-bottom: 45px;
  margin-bottom: 0;
}
.videoWrapper div,
.videoWrapper embed,
.videoWrapper object {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  top: 0;
}
.wideScreen {padding-bottom:56.25%;}
.fourBYthree {padding-bottom:75%;}
.chrome_25 {padding-top:25px;}
.chrome_35 {padding-top:35px;}
```

