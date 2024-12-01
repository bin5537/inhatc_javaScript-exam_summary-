```
class 이용 (상속)
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
        class Rectangle {
            constructor(width, height) {
                this.width = width;
                this.height = height;
            }

            getPerimeter() {
                return 2 * (this.width + this.height);
            }

            getArea() {
                return this.width * this.height;
            }
        }

        class Square extends Rectangle {
            constructor(length) {
                super(length, length);
            }
        }

        const rect = new Rectangle(10, 20);
        const square = new Square(10);
        document.write(`직사각형의 둘레: ${rect.getPerimeter()}<br>`);
        document.write(`직사각형의 넓이: ${rect.getArea()}<br>`);
        document.write(`ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ<br>`);
        document.write(`정사각형의 둘레: ${square.getPerimeter()}<br>`);
        document.write(`정사각형의 넓이: ${square.getArea()}<br>`);
    </script>
</body>

</html>
```

## 코드 설명

```js
// Rectangle 클래스 정의
class Rectangle {
    // 넓이와 높이를 초기화 하는 생성자
    constructor(width, height) {
        this.width = width;
        this.height = height;
    }

    // getPerimeter() 메서드 생성
    getPerimeter() {
        // 2 * (넓이 + 높이) 값을 반환
        return 2 * (this.width + this.height);
    }

    // getArea() 메서드 생성
    getArea() {
        // 넓이 * 높이 값을 반환
        return this.width * this.height;
    }
}

// Square 클래스는 Rectangle에 상속
class Square extends Rectangle {
    constructor(length) {
        // 부모 클래스의 생성자를 호출하여 넓이와 높이를 불러온 length(동일하게) 전송
        super(length, length);
    }
}

// rect변수에 Rectangle 객체 생성 후 저장
const rect = new Rectangle(10, 20);
// square변수에 Square 객체 생성 후 저장
const square = new Square(10);

// document.write를 통해 각각 출력
document.write(`직사각형의 둘레: ${rect.getPerimeter()}<br>`);
document.write(`직사각형의 넓이: ${rect.getArea()}<br>`);
document.write(`ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ<br>`);
document.write(`정사각형의 둘레: ${square.getPerimeter()}<br>`);
document.write(`정사각형의 넓이: ${square.getArea()}<br>`);
```