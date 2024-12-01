```
setAttribute를 이용해 객체 속성 설정
```

## 코드

```html
<!DOCTYPE html>
<html lang="ko">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <img src="" alt="" class="rect">
    <img src="" alt="" class="rect">
    <img src="" alt="" class="rect">
    <img src="" alt="" class="rect">
    <script>
        const rects = document.querySelectorAll(".rect");
        rects.forEach((rect, index) => {
            const width = (index + 1) * 100;
            const img = `media/img${index + 1}.png`;
            rect.setAttribute("src", img);
            rect.setAttribute("width", `${width}px`);
        })
    </script>
</body>

</html>
```

## 코드 설명

```js
// querySelectorAll() 을 통해 .rect 요소를 모두 불러옴
const rects = document.querySelectorAll(".rect");

// rects의 각 요소와 인덱스에 대해 반복 실행
rects.forEach((rect, index) => {

})

// width 변수 생성후 값은 (rects의 인덱스 + 1) * 100
const width = (index + 1) * 100;

// img 변수 생성후 이미지 경로는 `media/img${index + 1}.png` 
// rect의 index가 0인 경우 media/img1.png로 적용되는 형식
const img = `media/img${index + 1}.png`;

// 해당되는 rect의 src 속성에 img값을 삽입
rect.setAttribute("src", img);

// 해당되는 rect의 width 속성에 ${width}px값을 삽입
rect.setAttribute("width", `${width}px`);
```