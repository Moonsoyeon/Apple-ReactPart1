[CodingApple](https://online.codingapple.com/course/react-basic/)

## React 리액트 기초부터 쇼핑몰 프로젝트까지!
-----
배울 내용

    – class 문법없이 개발하는 2020스타일 easy-mode 리액트

    – 컴포넌트, Props, State를 이용한 웹앱 개발

    – 리액트로 HTML 모듈화해서 개발하는 법

    – JSX for 반복문, 이벤트 핸들러 등 어떻게 쓰는지 정확히 알려줌

    – 리액트 CLI로 프로젝트 생성, 관리, 빌드하는 법

    – Redux와 context API로 데이터 관리

    – Ajax 등으로 서버 API 요청하는법 (을 배울텐데 Ajax가 뭔지 모르니까 그것부터)

    – 라우터로 페이지 나누기

    – 리액트에서 CSS 스타일링 잘하는 법 (styled component, SASS)

    – import/destructuring/arrow function 등 필요한 ES6 문법들

    – 스마트폰에 설치가능한 Progressive Web App으로 리액트사이트 발행하기

    – (포트폴리오 자랑용) github pages를 이용해 사이트 발행
    
-----

### First Commit

part 1. input 다루기 2 : 블로그 글 발행

-----

<summary>리스트</summary>   

1-3 JSX를 이용해 HTML 페이지 제작해보는건 처음이겠죠

    - 리액트에서 class=""를 넣고 싶다면 className=""

    - 데이터바인딩 var data = '안녕하세요'; <div>{data}</div>

    - <div style = {{ color : 'blue', fontSize : '30px' }}>글씨</div>
      -> {속성명 : '속성값} 대쉬(-) 불가능, 붙여쓰고 앞글자를 대문자로 치환

1-4 중요한 데이터는 변수말고 리액트 state로 만들랬죠

    - state를 쓰는 이유
      -> 변수가 변경될 때 자동으로 관련된 HTML을 재렌더링되게 만들고 싶어서
      -> 수정사항이 자동으로 웹페이지에 스무스~하게 반영되게 만들고 싶어서

    - let [a, b] = useState('ㅇㅇㅇㅇ');
      -> a : 실제 저장할 데이터, b : 저장할 데이터를 변결시킬 함수
      -> 데이터바인딩 가능 <h3>{a}</h3> => <h3>ㅇㅇㅇㅇ<h3>
      -> Array, Object 가능 let [a, b] = useState(['ㅇㅇ', 'ㄴㄴ']);
