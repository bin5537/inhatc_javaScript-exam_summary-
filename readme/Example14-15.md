```
애니메이션 효과제어
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

        body {
            padding: 30px;
        }

        .btnWrap {
            margin-bottom: 10px;
        }

        .wrap {
            max-width: 600px;
            border: 1px solid #000;
        }

        .txt1 {
            width: 10%;
            text-align: center;
            background-color: aqua;
        }
    </style>
</head>

<body>
    <p class="btnWrap">
        <button class="backBtn">Back</button>
        <button class="goBtn">Go</button>
    </p>
    <div class="wrap">
        <p class="txt1">내용1</p>
    </div>

    <script>
        var txt1 = $(".txt1");
        $(".btnWrap button").on("click", function () {
            if (!txt1.is(":animated")) {
                if ($(this).hasClass("backBtn")) {
                    txt1.animate({
                        "margin-left": "0px"
                    }, 2000);
                } else {
                    txt1.animate({
                        "margin-left": "540px"
                    }, 2000);
                }
            }
        });
    </script>
</body>

</html>
```

## 코드 설명

```js
// txt1 변수에 .txt1 요소를 저장
var txt1 = $(".txt1");

// .btnWrap 내 모든 button 요소에 click 이벤트 발생시 실행
$(".btnWrap button").on("click", function () {

    // txt1 요소가 현재 에니메이션 중인지 확인
    if (!txt1.is(":animated")) {

        // 클릭된 요소의 class가 backBtn이면 실행
        if ($(this).hasClass("backBtn")) {
            // txt1 요소의 margin-left를 0px로 이동시키는 에니메이션 실행
            txt1.animate({
                "margin-left": "0px"
            }, 2000);

        // backBtn 버튼이 아닌경우 실행
        } else {
            // txt1 요소의 margin-left를 540px로 이동시키는 에니메이션 실행
            txt1.animate({
                "margin-left": "540px"
            }, 2000);
        }
    }
});
```