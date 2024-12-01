```
removeChild를 이용해 요소 제거
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
    <h1>제거 대상 문서 객체</h1>
    <script>
        setTimeout(() => {
            const h1 = document.querySelector("h1");
            document.body.removeChild(h1);
        }, 3000);
    </script>
</body>

</html>
```

## 코드 설명

```js
// setTImeout을 이용하여 3초후(3000) 실행되도록 설정
setTimeout(() => {
}, 3000);

// h1 변수를 생성하고 h1 태그를 불러와 저장
const h1 = document.querySelector("h1");

// removeChild를 이용하여 body에서 h1을 제거
document.body.removeChild(h1);
```