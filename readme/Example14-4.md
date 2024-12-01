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
    <style>
        h1 {
            user-select: none;
        }
    </style>
</head>

<body>
    <h1>클릭 횟수: </h1>
    <script>
        let counter = 0;
        const h1 = document.querySelector("h1");
        
        h1.addEventListener("click", (e) => {
            counter ++;
            h1.textContent = `클릭 횟수: ${counter}`;
        });
    </script>
</body>

</html>
```

## 코드 설명

```css
/* style 속성에서 user-select: none 속성은 드래그 방지 용도 */
h1 {
    user-select: none;
}
```

```js
// counter라는 변수를 저장 후 값은 0으로 설정 (값이 계속 변경되어야 해서 0을 부여)
let counter = 0;

// h1라는 변수 생성 후 querySelector을 이용해 h1을 저장
const h1 = document.querySelector("h1");

// h1에 addEventListener를 이용해 click 이벤트 발생하는 경우 함수 실행
h1.addEventListener("click", (e) => {
});

// counter ++를 이용해 1씩 증가
counter ++;
// h1의 텍스트 내용을 `클릭 횟수: ${counter}`
h1.textContent = `클릭 횟수: ${counter}`;
```