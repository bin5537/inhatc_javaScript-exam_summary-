```
이벤트 등록
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
</head>

<body>
    <p><button id="btn1">버튼1</button></p>
    <p><button id="btn2">버튼2</button></p>
    <p class="txt"></p>

    <script>
        $("#btn1").data("text", "javascript").on({
            "mouseover": overFnc,
            "mouseout": outFnc
        });

        $("#btn2").data("text", "welcome").on({
            "mouseover": overFnc,
            "mouseout": outFnc
        });

        function overFnc() {
            $(".txt").text($(this).data("text"));
        }

        function outFnc() {
            $(".txt").text("");
        }
    </script>
</body>

</html>
```

## 코드 설명

```js
// .data("text", "babo") 설정시 html에서 예시로
// <button data-text"babo"></button> 형식으로 표시


// #btn1에 데이터를 저장 후 이벤트 발생시 실행
$("#btn1").data("text", "javascript").on({
    // 마우스가 올라갔을경우 overFnc 함수 실행
    "mouseover": overFnc,
    // 마우스가 벗어났을경우 overFnc 함수 실행
    "mouseout": outFnc
});

// #btn1에 데이터를 저장 후 이벤트 발생시 실행
$("#btn2").data("text", "welcome").on({
    // 마우스가 올라갔을경우 overFnc 함수 실행
    "mouseover": overFnc,
    // 마우스가 벗어났을경우 overFnc 함수 실행
    "mouseout": outFnc
});

// overFnc 함수 생성
function overFnc() {
    // .txt의 텍스트를 현재 요소의 data-text를 불러와서 변경
    $(".txt").text($(this).data("text"));
}

// outFnc 함수 생성
function outFnc() {
    // .txt의 텍스트를 비움
    $(".txt").text("");
}
```