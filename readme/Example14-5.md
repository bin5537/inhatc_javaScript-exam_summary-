```
class 이용
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
        class Student {
            constructor(name, kor, eng, math, sc) {
                this.name = name;
                this.kor = kor;
                this.eng = eng;
                this.math = math;
                this.sc = sc;
            }

            getSum() {
                return this.kor + this.eng + this.math + this.sc;
            }

            getAvg() {
                return this.getSum() / 4;
            }

            toString() {
                return `${this.name} \t ${this.getSum()} \t ${this.getAvg().toFixed(2)}`;
            }
        }

        const students = [];
        students.push(new Student("구름", 87, 98, 76, 95));
        students.push(new Student("별이", 85, 65, 97, 94));
        students.push(new Student("겨울", 96, 37, 68, 69));
        students.push(new Student("바다", 68, 85, 88, 86));

        let output = "이름 \t 총점 \t 평균\n";
        for (const std of students) {
            output += std.toString() + "\n";
        }
        document.write(`<pre>${output}</pre>`);
    </script>
</body>

</html>
```

## 코드 설명

```js
// Student 클래스 정의
class Student {
}

constructor(name, kor, eng, math, sc) { // 학생 정보를 초기화하는 생성자
    this.name = name; // 학생 이름
    this.kor = kor;   // 국어 점수
    this.eng = eng;   // 영어 점수
    this.math = math; // 수학 점수
    this.sc = sc;     // 과학 점수
}

// getSum() 메서드 생성
getSum() { 
    // 과목 점수의 합계 반환
    return this.kor + this.eng + this.math + this.sc;
}

// getAvg() 메서드 생성
getAvg() {
    // 총점을 과목 수(4)로 나눈값 반환
    return this.getSum() / 4;
}

// toString() 메서드 생성
toString() {
    // 이름, 총점, 평균(소수점 둘째 자리까지) 반환
    return `${this.name} \t ${this.getSum()} \t ${this.getAvg().toFixed(2)}`; 
}

// students라는 비어있는 배열 생성
const students = [];

// push 메서드를 이용해 Student라는 생성자를 호출하여 새 객체르 생성 후 데이터 삽입
students.push(new Student("구름", 87, 98, 76, 95));
students.push(new Student("별이", 85, 65, 97, 94));
students.push(new Student("겨울", 96, 37, 68, 69));
students.push(new Student("바다", 68, 85, 88, 86));

// output 변수 생성 후 "이름 \t 총점 \t 평균\n" 삽입
let output = "이름 \t 총점 \t 평균\n";

// students에 저장된 값을 반복하여 std로 하나씩
for (const std of students) {
}

// output에 각 학생의 정보를 문자열로 변환 후 output에 추가
output += std.toString() + "\n";

// document.write를 이용해 output을 출력, \t를 화면에 유지하기 위해 pre 태그 사용
document.write(`<pre>${output}</pre>`);
```