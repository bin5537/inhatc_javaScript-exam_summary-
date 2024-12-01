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
    <p><button class="btn1">Mouse Over/Mouse Out</button></p>
    <p class="txt1">내용1</p>

    <p><button class="btn2">Hover</button></p>
    <p class="txt2">내용2</p>

    <script>
        $(".btn1").on({
            "mousover": function() {
                $(".txt1").css("background-color", "yellow");
            },
            "mouuseout": function() {
                $(".txt1").css("background", "none");
            }
        });

        $(".btn2").hover(function() {
            $(".txt2").css("background-color", "aqua");
        }, function() {
            $(".txt2").css("background", "none");
        })
    </script>
</body>

</html>
```

## 코드 설명

```js
// .btn1의 이벤트 발생시
$(".btn1").on({
    // 마우스를 .btn1 위에 올리면 실행
    "mousover": function() {
        // .txt1 요소의 background-color를 yellow
        $(".txt1").css("background-color", "yellow");
    },
    // 마우스를 .btn1에서 벗어나면 실행
    "mouuseout": function() {
        // .txt1 요소의 background를 none
        $(".txt1").css("background", "none");
    }
});

// .btn2에 hover 이벤트 발생시
$(".btn2").hover(function() {
    // .txt2 요소의 bacckground-color를 aqua
    $(".txt2").css("background-color", "aqua");
    
    // 마우스가 .btn2에서 벗어나면 실행
}, function() {
    // .txt2 요소의 background를 none으로
    $(".txt2").css("background", "none");
})
```