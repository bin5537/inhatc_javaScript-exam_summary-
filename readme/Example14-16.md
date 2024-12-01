```
슬라이드
```

## 코드

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://code.jquery.com/jquery-3.7.1.js"></script>
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .slide {
            margin: 0 auto;
            position: relative;
            width: 1000px;
            height: 600px;
            overflow: hidden;
        }

        .slide ul {
            position: relative;
            top: 0;
            left: 0;
            width: 8000px;
            font-size: 0;
        }

        .slide ul li {
            display: inline-block;
        }

        #back {
            position: absolute;
            top: 250px;
            left: 0;
            cursor: pointer;
            opacity: 0.3;
            z-index: 1;
        }

        #next {
            position: absolute;
            top: 250px;
            right: 0;
            cursor: pointer;
            opacity: 0.3;
            z-index: 1;
        }
    </style>
</head>

<body>
    <div class="slide">
        <img src="./media/back.gif" alt="" id="back">
        <img src="./media/next.gif" alt="" id="next">
        <ul>
            <li><img src="./media/img1.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img2.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img3.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img4.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img5.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img6.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img7.PNG" width="1000" height="600" alt=""></li>
            <li><img src="./media/img8.PNG" width="1000" height="600" alt=""></li>
        </ul>
    </div>

    <script>
        var medias;
        var media_count;
        var media_position = 1;

        medias = $(".slide ul");
        media_count = medias.children().length;

        $("#back").click(function () {
            back();
        });
        $("#next").click(function () {
            next();
        });

        function back() {
            if (1 < media_position) {
                medias.animate({
                    left: "+=1000px"
                });
                media_position--;
            } else {
                medias.animate({
                    left: "-=7000px"
                });
                media_position = 8;
            }
        }

        function next() {
            if (media_count > media_position) {
                medias.animate({
                    left: "-=1000px"
                });
                media_position++;
            } else {
                medias.animate({
                    left: "+=7000px"
                });
                media_position = 1;
            }
        }
    </script>
</body>

</html>
```

## 코드 설명

```js
// 변수 선언
var medias;             // 슬라이드 요소 변수
var media_count;        // 슬라이드 개수
var media_position = 1; // 현재 슬라이드 위치 (초기값: 1)

medias = $(".slide ul");                // 슬라이드 요소를 .slide ul로 지정
media_count = medias.children().length; // 슬라이드 개수를 슬라이드 요소의 자식요소의 길이로

// #back 클릭시 back 함수 실행, #next 클릭시 next 함수 실행
$("#back").click(function () {
    back();
});

$("#next").click(function () {
    next();
});

// back 함수 생성
function back() {
    // 현재 슬라이드 위치가 1보다 큰 경우
    if (1 < media_position) {
        // medias를 left 1000px씩 증가 (에니메이션 효과)
        medias.animate({
            left: "+=1000px"
        });
        // 현재 위치를 하나씩 감소
        media_position--;
    // 현재 슬라이드 위치가 1보다 크지 않은경우
    } else {
        // medias를 left 7000px씩 감소 (에니메이션 효과)
        medias.animate({
            left: "-=7000px"
        });
        // 현재 위치를 8으로 설정
        media_position = 8;
    }
}

// next 함수 생성
function next() {
    // 현재 위치가 슬라이드 개수보다 작은 경우
    if (media_count > media_position) {
        // medias를 1000px씩 감소 (에니메이션 효과)
        medias.animate({
            left: "-=1000px"
        });
        // 현재 위치를 하나씩 증가
        media_position++;
    // 현재 위치가 슬라이드 개수보다 작지 않은 경우
    } else {
        // medias를 left 7000px씩 증가 (에니메이션 효과)
        medias.animate({
            left: "+=7000px"
        });
        // 현재 위치를 1로 설정
        media_position = 1;
    }
}
```