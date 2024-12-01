```
이벤트 객체 생성
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
    <button onclick="openTextFile()">Open</button>
    <p class="zoomBtnZone">
        <button class="zoomOutBtn">-</button>
        <button class="originBtn">100%</button>
        <button class="zoomInBtn">+</button>
    </p>
    <hr>
    <p class="fontSize">14px</p>
    <div id="output"></div>

    <script>
        function openTextFile() {
            let input = document.createElement("input");
            input.type = "file";
            input.accept = "text/plain";
            input.onchange = function (e) {
                let file = e.target.files[0];
                let reader = new FileReader();
                reader.onload = function () {
                    output.innerText = reader.result;
                }
                reader.readAsText(file, "utf-8");
            }
            input.click();
        }
        
        // jQuery
        let baseFontsize = 14;
        const defaultFontSize = 14;
        $(".zoomBtnZone button").on("click", zoomInOut);

        function updateOriginBtnText() {
            let percent = Math.round((baseFontsize / defaultFontSize) * 100);
            $(".originBtn").text(percent + "%");
        }

        function zoomInOut() {
            if ($(this).hasClass("zoomOutBtn")) {
                if (baseFontsize <= 8) return false;
                baseFontsize--;
            } else if ($(this).hasClass("zoomInBtn")) {
                if (baseFontsize >= 30) return false;
                baseFontsize++;
            } else if ($(this).hasClass("originBtn")) {
                baseFontsize = defaultFontSize;
            }

            $(".fontSize").text(baseFontsize + "px");
            $("#output").css("font-size", baseFontsize + "px");
            
            updateOriginBtnText();
        }

        updateOriginBtnText();
    </script>
</body>

</html>
```

## 코드 설명

```html
<!-- button을 클릭(onclick) 한 경우 openTextFile() 함수를 실행 -->
<button onclick="openTextFile()">Open</button>
```

```js
// openTextFile() 함수 생성
function openTextFile() {
    // 파일 선택을 위한 input 요소 생성
    let input = document.createElement("input");
    // input 요소의 타입 지정
    input.type = "file";
    input.accept = "text/plain"; // 텍스트 파일만 로드

    // 파일이 선택 되었을때 실행되는 이벤트
    input.onchange = function (e) {
        // 선택된 파일을 불러옴
        let file = e.target.files[0];
        // 파일 내용을 읽기 위해 FileReader 객체 생성
        let reader = new FileReader();
        // 파일읽기가 완료 되었을 경우 실행
        reader.onload = function () {
            // 읽은 텍스트 파일 내용을 output 요소의 텍스트로 표시
            output.innerText = reader.result;
        }

        // 파일을 텍스트로 읽기 시작
        reader.readAsText(file, "utf-8");
    }

    // 파일 선택창 열기
    input.click();
}

// jQuery로 폰트 사이즈 설정

// 기본 폰트를 14
let baseFontsize = 14;
// 초기 기본 폰트를 14 (변경되지 않음)
const defaultFontSize = 14;

// .zoomBtnZone의 모든 버튼 클릭시 zoomInOut 함수 실행
$(".zoomBtnZone button").on("click", zoomInOut);

// updateOriginBtnText() 함수 생성
function updateOriginBtnText() {
    // 현재 폰트 크기의 비율을 백분율로 계산
    let percent = Math.round((baseFontsize / defaultFontSize) * 100);
    // .originBtn에 현재 텍스트 비율을 표시
    $(".originBtn").text(percent + "%");
}

// zoomInOut 함수 생성
function zoomInOut() {
    // zoomOutBtn 버튼 클릭시
    if ($(this).hasClass("zoomOutBtn")) {
        // 폰트 크기가 8px 이하로 설정 불가능 하도록 제한
        if (baseFontsize <= 8) return false;
        // 폰트 크기를 1씩 감소
        baseFontsize--;
    // zoomInBtn 버튼 클릭시
    } else if ($(this).hasClass("zoomInBtn")) {
        // 폰트 크기가 30px 이상으로 설정 불가능 하도록 제한
        if (baseFontsize >= 30) return false;
        // 폰트 크기를 1씩 증가
        baseFontsize++;
    // originBtn 버튼 클릭시
    } else if ($(this).hasClass("originBtn")) {
        // 폰트 크기를 변경되지 않는 초기 기본폰트 사이즈로 변경
        baseFontsize = defaultFontSize;
    }

    // 현재 폰트 사이즈를 .fontSize 텍스트로 표시
    $(".fontSize").text(baseFontsize + "px");
    // #output 내 모든 font-size를 변경되는 폰트 사이즈로 지정
    $("#output").css("font-size", baseFontsize + "px");
    
    // updateOriginBtnText() 함수 실행
    updateOriginBtnText();
}

// 초기 실행: 초기 사이즈를 표기해야하므로 실행시킴
updateOriginBtnText();
```