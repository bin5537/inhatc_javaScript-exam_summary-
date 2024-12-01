```
appendChild를 이용해 동적으로 생성
```

## 코드

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script>
        const header = document.createElement("h");
        header.textContent = "문서객체 동적으로 생성하기";
        header.style.color = "white";
        header.style.backgroundColor = "black";
        header.style.fontSize = "20px";
        document.body.appendChild(header);
    </script>
</body>

</html>
```

## 코드 설명

```js
// header라는 변수를 생성하고 createElement를 통해 h라는 요소를 저장
const header = document.createElement("h");

// header의 텍스트 내용을 "문서객체 동적으로 생성하기"로 변경
header.textContent = "문서객체 동적으로 생성하기";

// header의 스타일을 변경
header.style.color = "white";           // color를 white
header.style.backgroundColor = "black"; // backgroundColor를 black
header.style.fontSize = "20px";         // fontSize를 20px

// appendChild를 이용하여 body에 위에서 생성한 header를 추가
document.body.appendChild(header);
```