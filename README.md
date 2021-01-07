[CodingApple](https://online.codingapple.com/course/react-basic/)

## React 리액트 기초부터 쇼핑몰 프로젝트까지!
<details>
<summary>배울 내용</summary>

    – class 문법 없이 개발하는 2020스타일 easy-mode 리액트

    – 컴포넌트, Props, State를 이용한 웹앱 개발

    – 리액트로 HTML 모듈화해서 개발하는 법

    – JSX for 반복문, 이벤트 핸들러 등 어떻게 쓰는지 정확히 알려줌

    – 리액트 CLI로 프로젝트 생성, 관리, 빌드하는 법

    – Redux와 context API로 데이터 관리

    – Ajax 등으로 서버 API 요청하는 법 (을 배울 텐데 Ajax가 뭔지 모르니까 그것부터)

    – 라우터로 페이지 나누기

    – 리액트에서 CSS 스타일링 잘하는 법 (styled component, SASS)

    – import/destructuring/arrow function 등 필요한 ES6 문법들

    – 스마트폰에 설치 가능한 Progressive Web App으로 리액트사이트 발행하기

    – (포트폴리오 자랑용) github pages를 이용해 사이트 발행

</details>

-----

<details>
<summary>1-3</summary>
JSX를 이용해 HTML 페이지 제작해보는 건 처음이겠죠

    - 리액트에서 class=""를 넣고 싶다면 className=""

    - 데이터바인딩 var data = '안녕하세요'; <div>{ data }</div>
      -> { } 꼭 중괄호 안에

    - <div style = {{ color : 'blue', fontSize : '30px' }}>글씨</div>
      -> {속성명 : '속성값} 대쉬(-) 불가능, 붙여쓰고 앞글자를 대문자로 치환
</details>

<details>
<summary>1-4</summary>
중요한 데이터는 변수 말고 리액트 state로 만들랬죠

    - state를 쓰는 이유
      -> 변수가 변경될 때 자동으로 관련된 HTML을 재렌더링되게 만들고 싶어서
      -> 수정사항이 자동으로 웹페이지에 스무스~하게 반영되게 만들고 싶어서

    - let [a, b] = useState('ㅇㅇㅇㅇ');
      -> a : 실제 저장할 데이터, b : 저장할 데이터를 변결시킬 함수
      -> 데이터바인딩 가능 <h3>{a}</h3> => <h3>ㅇㅇㅇㅇ<h3>
      -> Array, Object 가능 let [a, b] = useState(['ㅇㅇ', 'ㄴㄴ']);
</details>

<details>
<summary>1-5</summary>
버튼에 기능 개발을 해보자 & 리액트 state 변경하는 법

    - 리액트에서 특정 HTML 요소를 클릭했을 때 자바스크립트를 실행하고 싶으면
      -> <div onClick = { 실행할 함수 }>
      -> Click이 대문자, {} 중괄호 사용, 그냥 코드가 아닌 함수를 적어야 함
      -> ex) <div onClick = { 함수이름 }>
             <div onClick = { function(){ 실행할 코드 } }>
             <div onClick = { () => { 실행할 코드 } }>

    - state는 변수와는 다르게 값을 변경할 때 지정된 변경 함수를 써야 함
      -> ㅇㅇ변경(대체할 데이터) 
      -> ex) <span>👍</span> 을 눌렀을 때 따봉이라는 state를 1 증가하려면 어떻게 해야할까요?
             <span onClick = { { () => { 따봉변경(따봉 + 1) } } }>
</details>

<details>
<summary>1-6</summary>
숙제 해설 : 블로그 글 수정버튼 만들기

    - 원래 자바스크립트 내에서 array나 object 자료형은 = 등호로 복사하면 각각 별개의 자료형이 생성되는게 아니라 값을 공유함
      -> ex) var data1 = [1, 2, 3]; var data2 = data1;
         => data1과 data2는 각각 [1, 2, 3]을 별개로 저장하는 게 아닌 똑같은 값을 공유함
         => data1을 변경하면 data2도 자동으로 변경됨
      -> state도 = 등호를 이용해서 복사하면 문제가 일어나기 때문에 완전히 개별 복사본을 만들어주는 카피를 해야 함
         => ex) var 새로운array = [...원본array]
         => function 제목바꾸기() {
                var newArray = [...글제목];
                newArray[0] = '여자코트 추천';
                글제목변경( newArray );
            } 
</details>

<details>
<summary>1-7</summary>
React Component : 많은 div들을 한 단어로 줄이고 싶은 충동이 들 때

    - return () 안에 HTML을 넣을 때 태그 2개를 평행하게 넣을 수 없음
      -> 굳이 쓰고 싶다면
         <div>
            <div></div>
            <div></div> 
         </div>

    - Component : 리액트에서 제공하는 긴 HTML을 한 단어로 깔끔하게 치환해서 넣을 수 있는 문법
      -> 함수 만들 듯, 변수 만들 듯 한 단어로 치환해서 원하는 곳에 꽂아넣을 수 있음
    
    - 방법
      1. function을 이용해서 함수를 하나 만들기
      2. 그 함수 안에 return() 안에 원하는 HTML을 담기
      3. 원하는 곳에서 <Modal></Modal> 이라고 사용했을 때 축약한 HTML이 등장
      -> 축약한 HTML 덩어리를 Component 라고 칭함
      -> ex)
         function App (){
            return (
                <div>
                    HTML 잔뜩있는 곳
                    ...
                    <Modal></Modal>
                </div>
            )
         }

         function Modal(){
             return (
                 <div className="modal">
                    <h2>제목</h2>
                    <p>날짜</p>
                    <p>상세내용</p>
                 </div>
            )
         }
        
    - Component의 특징
      -> Component 이름 지을 땐 보통 영어 대문자로 시작
      -> return() 안에 태그들이 평행하게 여러 개 들어갈 수 없음 ex) <div>, <></>
      -> Component 위치는 보통 funcion App(){} 와 나란히 만듦
         -> 보통 컴포넌트 안에다가 컴포넌트를 만들진 않기 때문
      -> Component 안에 미리 만들어둔 Component 집어넣기도 가능

    - 어떤 HTML들을 Component 만드는게 좋을까
      -> 사이트에 반복해서 출현하는 HTML 덩어리들
      -> 내용이 자주 변경될 것 같은 HTML의 한 부분
      -> 다른 페이지를 만들 때
      -> 다른 팀원과 협업할 때 웹페이지를 컴포넌트 단위로 작업 분배

    - Component 단점
      -> HTML을 깔끔하게 쓰려고 함수 자체를 많이 만드는 것 자체로 관리가 힘듦
      -> <Modal>이라는 컴포넌트가 App(){} 안에 있는 state를 사용하고 싶을 때,
         그냥 바로 쓸 수 없음
         => props라는 문법을 이용해 state를 <Modal>까지 전해줘야 사용 가능
</details>

<details>
<summary>1-8</summary>
클릭하면 동작하는 UI (모달창) 만드는 법

    - 리액트는 중괄호 내에서 if문을 사용할 수 없어서 삼항연산자를 사용해야 함
      -> 조건식 ? 조건식 참일 때 실행할 코드 : 조건식 거짓일 때 실행할 코드 
</details>

<details>
<summary>1-9</summary>
map : 많은 div들을 반복문으로 줄이고 싶은 충동이 들 때

    - 반복문도 {중괄호} 안에서 { for (){} } 이렇게 넣을 수 있지않을까 생각할 수 있지만 {중괄호} 안에는 변수, 함수만 입력 가능함
      -> 중괄호 안에서 쓸 수 있는 map이란 반복문 이용
    
    - 방법
      ex1) 
      var 어레이 = [2, 3, 4];
      어레이.map(function(){
      });
        => 모든 array에 붙일 수 있으며 소괄호 안에 콜백 함수 하나 넣는 게 기본, map 안의 코드가 어레이 자료의 갯수만큼 실행됨(ex1에서 3번)

      ex2)
      var 어레이 = [2, 3, 4];
      어레이.map(function(a){
        return a * 10
      });
        => 콜백 함수 소괄호 안에 파라미터를 아무 이름이나 입력해주면(ex2에서 a), a라는 파라미터가 어레이 안에 있던 모든 자료를 하나씩 출력해주는 역할을 함 => [20, 30, 40]이 됨

      ex3)
      var 어레이 = [2, 3, 4];
      var newArray = 어레이.map(function(a){
          return a * 10
      });
        => 참고로 map 함수는 원본 자료형을 변형시키지 않아서 보통 새로운 변수에 담아서 사용함
           newArray에는 [20,30, 40], 원래 어레이에는 [2, 3, 4]
      
    - JSX 안에서 map으로 반복문을 돌리고 싶으면
      1. 원하는 자료에다가 map을 붙이면 그 자료 갯수만큼 반복문 돌리기 가능
      2. 반복을 원하는 HTML을 return 안에 적으면 끝

      ex)
      <div>
        ~~~HTML 잔뜩~~~
        ...
        { 글제목.map(function(){      
            return (<div>안녕</div>)
        }) }
      </div>
        => 현재 글제목 array에는 3개의 데이터가 들어있으니 실행해보면 div도 3개가 남음
    
    - 반복된 HTML에 각각 다른 내용을 부여하고 싶다면
      ex)
      <div>
        ~~~HTML 잔뜩~~~
        ...
        { 글제목.map(function(a){
            return (
                <div className="list">
                  <h3>{ a }</h3>
                  ~~~HTML 잔뜩~~~
                </div>
            )
        }) }
      </div>
        
        -> 반복된 HTML 안에 onClick = {} 이런 거 넣어도 잘 작동함

    - 일반 for 반복문을 사용하고 싶다면
      -> 따로 함수를 만들어서 사용해야 함
      1. 따로 일반 함수를 만들고
      2. 함수 안에 HTML을 담을 array 자료를 하나 생성
      2. 함수 안에서 for 반복문을 이용해 array 내에 HTML을 추가
      4. 완성된 array를 return
      5. 함수를 원하는 곳에 { 함수명() } 데이터바인딩

      ex)
      function 반복된UI(){
        var 어레이 = [];
        for (var i = 0; i < 3; i++) {
            어레이.push(<div>안녕</div>)
        }
        return 어레이
      }
      return (
        <div>
            ~~~HTML 잔뜩~~~
            { 반복된UI() }
        </div>
      )


</details>