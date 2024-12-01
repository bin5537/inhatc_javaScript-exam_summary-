```
제이쿼리 위치 탐색자
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
    <h1>탐색 선택자</h1>
    <ul id="menu">
        <li>내용1</li>
        <li>내용2</li>
        <li>내용3</li>
        <li>내용4</li>
    </ul>

    <script>
        // even
        $("#menu li:even").css("background-color", "#ff0");
        $("#menu li:odd").css("background-color", "#0ff");

        // eq
        // $("#menu li").eq(2).css("background-color", "#ff0");
        // $("#menu li:lt(2)").css("background-color", "#0ff");
        // $("#menu li:gt(2)").css("background-color", "#ff0");
    </script>
</body>

</html>
```

## 코드 설명

```js
// #menu 내 li태그의 짝수의 css background-color를 #ff0
$("#menu li:even").css("background-color", "#ff0");

// #menu 내 li태그의 홀수의 css background-color를 #0ff
$("#menu li:odd").css("background-color", "#0ff");

// #menu 내 li태그의 index 2번 css background-color를 #ff0
$("#menu li").eq(2).css("background-color", "#ff0");

// #menu 내 li태그의 index 2번 전까지 css background-color를 #0ff
$("#menu li:lt(2)").css("background-color", "#0ff");

// #menu 내 li태그의 index 2번 후 모두 css background-color를 #ff0
$("#menu li:gt(2)").css("background-color", "#ff0");
```