⭐ COMMENTS
============

1 - 인라인 주석
--------

    // 내용


2 - 블록 주석
-----

    /*내용*/
    /*
      내용
      내용
      내용
    */

3 - CSS
----

- 자바스크립트의 블록 주석과 동일
- 인라인 주석은 지원하지 않음

4 - HTML
----

    <!-- 내용
     내용  -->
</br>
</br>


⭐ HTML
============

1 - HEAD
-----
- 브라우저에 절대 나타나지 않는 요소

2 - BODY
----
- 브라우저에 렌더링될 페이지 콘텐츠
❗ <script> 와 같은 특정 요소는 바디에 있어도 브라우저에 나타나지 않음
    
</br>
</br>


⭐ JAVASCRIPT CONSOLE
============

    console.log('main.js loaded');

- 콘솔: 프로그램을 진단할 때 사용하는 텍스트 전용 도구
- 단축키: ctrl + shift + j (크롬 브라우저)
- `console.log`: 메서드

</br>
</br>


⭐ JQUERY
============
   
    $(document).ready(function() {
      'use strict';
      console.log('main.js loaded');
    });

- 가장 대중적인 클라이언트 스크립트 라이브러리
- 자바스크립트 코드를 실행하기 전에 브라우저가 HTML을 전부 불러왔는지 확인
- 모든 자바스크립트 코드는 `$(document).ready(function() {` 과 `});` 사이에 들어감
- `'use strict';`: 인터프리터에서 코드를 엄격하게 처리하라는 의미
</br>
</br>

⭐ PAPER.JS 로 원 그리기
============

1 - HTML
----
    
    <canvas id="mainCanvas"></canvas>
    <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/paper.js/0.9.25/paper-full.min.js"></script>
    <script src="main.js"> </script>
    

- 가장 대중적인 그래픽 라이브러리로 간단한 원과 같은 도형을 그림
- `id`: 자바스크립트와 CSS에서 해당 요소를 쉽게 찾기 위함
- 캔버스 추가
</br>


2 - CSS
----

    #mainCanvas {
    width: 400px;
    height: 400px;
    border: solid 1px black;
    }

- 캔버스의 크기와 테두리 색 지정

</br>

3 - main.js
----

      paper.install(window);
      paper.setup(document.getElementById('mainCanvas'));
      
      paper.view.draw();

- `보일러플레이트(Boilerplate)`: 어떤 일을 하기 전에 먼저 실행해야 하는 코드

</br>

      var c = Shape.Circle(200, 200, 50);
      c.fillColor = 'green';

- 보일러플레이트 사이에 실제로 그림을 그리는 코드를 삽입해준다.
- 매개변수: 원 중앙의 x좌표, y좌표, 원의 반지름
</br>
</br>


⭐ FOR LOOP
============

     var c;
     for(var x=25; x<400; x+=50) {
        for(var y=25; y<400; y+=50) {
            c = Shape.Circle(x, y, 20);
            c.fillColor = 'green';
        }
    }

- 반복적인 작업 자동화하기
- 캔버스 전체에 바둑판 모양으로 64개의 원 그리기
- 초기값(25), 제한조건(400 미만), 증가분(50)
- x축과 y축에서 각각 반복
</br>
</br>

⭐ 사용자 입력 처리하기
============

     var tool = new Tool();

     tool.onMouseDown = function(event) {
        var c = Shape.Circle(event.point.x, event.point.y, 20);
        c.fillColor = 'green';
     };

- 툴(Tool) 객체를 통해 사용자 입력을 처리
- 객체를 만들고나면 이벤트 핸들러를 연결 가능
- `onMouseDown`: 사용자가 마우스를 클릭할 때마다 핸들러에 연결된 함수가 호출됨
</br>
</br>

⭐ 텍스트 추가하기
============

    var c= Shape.Circle(200, 200, 80);
    c.fillColor = 'black';
    var text = new PointText(200, 200);
    text.justification = 'center';
    text.fillColor = 'white';
    text.fontsize = 20;
    text.content = 'hello world';

- 텍스트의 배경이 되는 원을 만들고
- 텍스트 객체 `PointText` 생성
- 텍스트가 캔버스의 중앙에 위치
</br>
</br>
