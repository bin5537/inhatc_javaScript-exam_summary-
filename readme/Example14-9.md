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
    <ul id="myList">
        <li>내용1</li>
        <li>내용2</li>
        <li>내용3</li>
        <li>내용4</li>
    </ul>
    <script>
        $("#myList li").not("eq(2)").css("background-color", "yellow");
    </script>
</body>

</html>
```

## 코드 설명

```js
// #myList 내 li 요소중 index 2가 아닌것의 background-color를 yellow 적용
$("#myList li").not("eq(2)").css("background-color", "yellow");
```