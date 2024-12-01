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
    <ul id="menu1">
        <li>내용1-1</li>
        <li>내용1-2</li>
        <li>내용1-3</li>
        <li>내용1-4</li>
    </ul>
    <ul id="menu2">
        <li>내용2-1</li>
        <li>내용2-2</li>
        <li>내용2-3</li>
        <li>내용2-4</li>
    </ul>

    <script>
        $("#menu1 li:nth-child(1)").css("background-color", "#ff0");
        $("#menu1 li:nth-child(2n)").css("border", "2px dashed #f00");
        $("#menu1 li:nth-last-child(2)").css("background-color", "#0ff");
    </script>
</body>

</html>
```

## 코드 설명

```js
// #menu 내 li태그 요소이 부모 내에서 1번째 자식요소의 css background-color를 #ff0
$("#menu1 li:nth-child(1)").css("background-color", "#ff0");

// #menu 내 li태그 요소이 부모 내에서 2의배수 자식요소의 css background-color를 #ff0
$("#menu1 li:nth-child(2n)").css("border", "2px dashed #f00");

// #menu 내 li태그 요소이 부모 내에서 뒤에서 2번째 자식요소의 css background-color를 #ff0
$("#menu1 li:nth-last-child(2)").css("background-color", "#0ff");
```