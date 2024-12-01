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
    <p><button class="btn1">버튼</button></p>
    <p>내용1</p>

    <p><button class="btn2">버튼</button></p>
    <p>내용2</p>

    <script>
        $(".btn1").click(function() {
            $(".btn1").parent().next().css("color", "#f00");
        });
        $(".btn2").on("mouseover focus", function() {
            $(".btn2").parent().next().css("color", "#0f0");
        });
    </script>
</body>

</html>
```

## 코드 설명

```js
// .btn1에 click 발생시
$(".btn1").click(function() {
    // .btn1의 부모요소의 다음 형제요소 color를 #f00
    $(".btn1").parent().next().css("color", "#f00");
});

// .btn2에 마우스를 올리거나, 포커스 이벤트가 발생시 
// (focus는 키보드 탭 눌러서 이동하는거라 생각하면 됨)
$(".btn2").on("mouseover focus", function() {
    // .btn2의 부모요소의 다음 형제요소 color를 #0f0
    $(".btn2").parent().next().css("color", "#0f0");
});
```