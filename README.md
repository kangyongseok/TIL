# TIL
Today I learned

#181116
=========

> ## What is OAuth

OAuth 는 인터넷 사용자들이 비밀번호를 제공하지 않고 다른 웹사이트 상의 자신들의 정보에 대해 웹사이트나 애플리케이션의 접근 권한을 부여할 수 있는 공통적인 수단으로서 사용되는 접근위임을 위한 개방형표준이다.

OAuth 가 사용되기 전에는 인증방식의 표준이 없었기 때문에 기존의 기본인증인 아이디와 비밀번호를 사용하였는데, 이는 보안상 취약한 구조이다. - [위키백과](https://ko.wikipedia.org/wiki/OAuth)

> ## OAuth와 로그인

OAuth 와 로그인에는 차이가 있다.

사원증을 이용해 출입하는 회사일경우 회사 사원이 건물에 출입하는것이 *'로그인'* 이라면 OAuth는 방문증을 수령한 후 회사에 출입하는 *'외부손님'* 으로 비유 할 수 있다.

| 회사방문과정        | OAuth           |
| ------------- |:-------------:|
| 외부손님이 안내데스트에서 업무적인 목적으로 직원을 만나러 왔다고 말한다      | Request Token의 요청과 발급 |
| 안내 데스크에서는 직원에게 손님이 방문했다고 연락한다.      | 사용자 인증 페이지 호출      | 
| 직원이 안내 데스크로 찾아와 손님의 신원을 확인해 준다 | 사용자 로그인 완료      |
| 직원은 업무 목적과 인적 사항을 안내데스크에서 기록한다. | 사용자의 권한 요청 및 수락      |
| 안내데스크에서 손님에게 방문증을 발급해준다. | Access Token발급      |
| 직원과 고객은 정해진 장소로 이동해 업무를 진행한다. | Access Token을 이용해 서비스 정보 요청      |

내용 출처 - [네이버 D2](https://d2.naver.com/helloworld/24942)
<br/><br/>

> ## 결국보안
user 가 나의 서비스를 사용할 때 번거로운 로그인 절차 필요 없이 이미 가입된 타사의 정보를 입력하게 요청하여 서비스를 이용가능하게 만들어 주는것 여기서 user, My, 제3자 이렇게 셋다 껄끄러운 상황이된다.
1. **user(Resource Owner)** 처음보는 서비스에서 다른데에서 사용하는 비밀번호를 노출해야하는 상황
2. **My(Client)** 해킹의 위협 보안의 위협에서 타사 서비스의 고객정보를 보호해야하는 생황
3. **제 3자(Resource Server)** 의도하지 않은 고객정보의 유출 및 보안의 위협

이러한 문제들을 해결하기 위해 나온것이 *'OAuth'* 제 3자 에서는 원래 user 가 사용하던 비밀 번호가 아닌 임시 비밀번호를 제공 이것이 *'Access Token'* 이것을 My 서비스에서 제출하는것을 통해서 제 3사에서 일정부분에 대해서 일정시간동안만 얻어와 사용하게 됨
<br/>

Blog: [How ReactJS Facebook OAuth Login](http://code-reading.tistory.com/65)<br/>
DEMO: [Git Demo](https://kangyongseok.github.io/Facebook-Login/)



#181121
=============
> ## Object
객체는 어떤것을 의미하며 이러한 단위화된 표현을 통해 개발을 더 쉽게 할 수 있다.

객체에는 여러가지 속성을 부여할 수 있으며, 특정동작을 할수 있도록 메소드를 부여할 수도있다.

```javascript
let kang_yong_seok = {
            name: "Kang Yong Seok",
            height: 165,
            wight: 60,
            position: "FrontEnd Developer",
            eat: () => {this.height > 65 ? console.log("과체중입니다.") : console.log("표준입니다.")}
        }

        kang_yong_seok.eat(); // 표준입니다.
        console.log(kang_yong_seok.name) // Kang Yong Seok
        console.log(kang_yong_seok) // 객체정보
```

> ## Class
클래스는 일종의 틀이다. 위의 객체는 한사람의 특징에 대해서만 나타낼수 있다면 클래스는 일정한 틀을 정해놓고 그 틀 안에서는 얼마든지 다양한 사람의 객체를 나타낼 수 있다. 이것은 템플릿처럼 사용이 가능하다.

클래스로 생성된 객체를 클래스의 인스턴스 라고도 한다.

JavaScript 에서는 클래스 개념이 없다. 모두 객체에 기반하고 있기때문이다. 그러나 Prototype 을 활용하면 클래스개념과 비슷하게 생성해 낼 수는 있다.

```javascript
let People = function() {};

        People.prototype = {
            name:String,
            age: Number,
            height:Number,
            weight:Number,
            position:String,
            eat:Function
        }

        let kang_yong_seok = new People();

        kang_yong_seok.name = "Kang Yong Seok";
        kang_yong_seok.height = 165;
        kang_yong_seok.weight = 60
        kang_yong_seok.age = 31

        let hong_gil_dong = new People();

        hong_gil_dong.name = "Hong Gil Dong";
        hong_gil_dong.position = "hero";
        hong_gil_dong.height = 170;

        console.log(kang_yong_seok) // 객체정보
        console.log(hong_gil_dong) 
```

# 181213 

## 프론트엔드직군 첫 면접



> 면접후기

설립한지 아직 3년밖에 안된 따끈따끈한 스타트업<br/>
웹에이전시업무를 기반으로 개발중인 소프트웨어가 따로있고<br/>
워라벨을 중요시하기때문에 야근은 안하려고한다<br/>
그러나 야근을 없애려면 일하는 시간중에 딴짓이나 어떤 여유를 가질시간은 없다<br/>
소규모로 계속 구성해나가기때문에 1명이서 해야할 업무가 포괄적이고 사수나 부사수없이 
혼자 맡은 파트의 업무를 다 진행해야한다.

---

> 받았던 질문

React Project 관련해서 완성된 결과물의 소스를 까본적이 있는지<br/>
웹으로 지원했는데 하이브리드앱에는 관심이 있는지<br/>
지금당장 소스를 받았을때 파악하는데 얼마나 걸릴지<br/>
업무가 주어졌을때 그때그때 필요한걸 찾아서 활용할 수 있는지<br/>

---

> 느낀점

일단 난 아직도 갈길이 멀구나 라고 느낌<br/>
들어가면 바로 실무 투입에 혼자 프론트파트를 다 맡아야하기에
부담감과 중압감 약간 무섭기도하지만 그만큼 내가 성장할 가능성은 높아보임<br/>
AWS 나 버전관리툴로 지라를 쓰는등 전반적으로 최신트랜드를 따라가려는것으로 보임<br/>
당장에 완성된 프로젝트를 찾아서 소스를 까보고 분석하는것부터 해봐야겠다는 생각이 들고<br/>
깃헙말고도 다른 버전관리 툴에 대해서 공부하고 알아볼 필요가 있겠다고 생각함

---

## 노마드코더의 Vanila Js 과정 수강 시작
* 가장 기초의 문법 설명으로 이어나가기 때문에 빠르게 개념만 잡기위해 단기간에 수강하려고함
* 뒤로갈수록 포트폴리오가 될만한 프로젝트를 만드는것같은데 아직 끝까지 보지않아서 수강이 끝나면 결과물과 함께 github 에 업로드 예정
* 이번 강의를 기준으로 생활코딩이라던지 타 강의중 개념잡고 넘어갈 강의들을 빠르게 학습하려고함

# 181214

## 노마드코더의 [초보자를위한 Vanila JS](https://academy.nomadcoders.co/courses/enrolled/435558) 수강완료

* 시간출력
* 사용자 입력 저장 및 출력
* 오늘할일 추가 및 삭제
* 현재위치와 날씨 온도 


# 181216

## 서면평가 내용 정리

> React 나 Vue 같은 프레임워크나 라이브러리들이 jQuery 보다 좋은점은 무엇인가

이 질문을 받고 들었던 생각은 딱 두가지였다.
* jQuery 는 최근 기피 대상이면서 걷어내고 모던한 웹에서는 더이상 인기도없고 쓰이지않는 추세인것
* jQuery 는 상대적으로 무겁고 또 속도 성능면에서 느리다.

반면에 최근 javascript 프레임워크, 라이브러리들은

* 빠른 성능에 초점을 맞추고있다. (변경된 부분만 랜더링)
* 최근 트렌드이며 유행이다.(구직사이트에서도 React개발자 공고가 많이 보인다.)
* 컴포넌트 개발방식으로 재사용이 가능하다.

이게 내가 가장 기본적으로 알고있는것이고 또 여러 커뮤니티나 블로그에서 쉽게 찾아볼 수 있는 비교내용이다.

개인적으로는 React를 사용하고있는데 컴포넌트개발방식이 꼭 조립식 레고 장난감을 맞추는것같아서 재미있는것같다. 

쉬운사용법과 이미 jQuery를 기반으로 만들어진 많은 라이브러리들이 있어서 생태계나 낮은러닝커브 손쉬운 개발면에서는 jQuery가 낫다고 생각한다.

그러나 jQuery가 굳이 최근 모던 프레임워크나 라이브러리들이랑 비교되는 이유는 사용자에게 더 나은 웹 앱에대한 경험을 준다는것과 인기있는 유명한 기업이나 소셜네트워크 등의 타이틀을 갖고 인기를 몰아가고있는 영향이 있는것같다.

어떤 사람들은 직접 DOM 에 접근하는 jQuery 와 virtualDOM 을 사용하는 React를 왜 비교하는지 모르겠다고 하는 분들도 있다.

사실 jQuery는 더이상 쓰지않는다 걷어낸다 라는 말들이 보이긴하지만 실제로는 jQuery는 아직도 많은곳에서 꽤 사용되고있는것같다.

더욱이 우리나라같은경우는 IE 의 점유율을 무시할수 없기때문에 크로스브라우징 때문이라도 무조건 jQuery 를 안쓸수 없는것도 현실인것같다.

직접적으로 큰 프로젝트에 참여하거나 만들어본 경험이 없어서 속도나 성능면에서의 이슈보다도 사실 취업의 문제와 또 계속 개발을 해 나가기위한 재미에 대한 요소가 더 크게 작용한것같다.

게다가 javascript 에 집중하면 React에 대한 접근은 더 쉬워지고 React Native 까지 영역을 넓힐수 있다는 장점도 크게 작용한것같다. 하나만 사용할줄 알면 웹이고 앱이고 뭐든 만들어 낼 수 있으니 jQuery 보다는 상대적으로 매력적인 요소가 많다.

VanilaJS 가 떳었던 이유도 사실 웹에서는 슬라이드 나 이벤트 등 비교적 한정적인 영역안에서만 기능을 사용하는데 그 몇가지 사용하자고 jQuery의 방대한 양의 코드와 용량을 지고갈 필요가 있나 에서 그럼 그냥 필요한것만 만들어서 쓰자로 나온 트랜드인것으로 알고있다. 게다가 모바일환경까지 생각하면 jQuery의 용량은 모바일의 성능저하를 야기할수있기 때문이기도 하다.

이미 제출은 했지만 이후 좀더 자료나 정보를 찾아보려고 시도를 했는데 명확한 결론은 사실 없었던것같고 어쩃든 사용자들이 많이 사용하는 인기있는 웹앱들이 많이 사용하고 있고 또 그것에 빠르게 익숙해져 가기때문에 사용자를 모으려면 관심을 갖게하려면 그 기술들을 활용하는것이 맞는것같다.

물론 이 과정에서 개발자또한 더 나은 개발환경, 클린코드, 가독성에 대한 좋은 경험을 갖는 이점도 생기는것같다.

---

> 프론트엔드개발 테스트프레임워크중에서 사용하는것이 있다면 설명하시오

이 글을 작성하게 된 계기가 이 질문때문이었다. 

이 질문에 대해서 답을 할 수 없었던것이 너무 뼈아프고 신경이 쓰인다.

그저 빨리 사용법을 익히고 포폴을 만들고 뭔가 생각하던것을 만들고 React를 어떻게 활용할 수 있는지만 생각했지 단위테스트에 대한 블로그 글이나 여러 자료들은 많이 봤지만 사실 직접 적용해보고 써본적은 없다는게 왜 그랬을까 싶을정도다.

그래서 어차피 정리하고 사용법도 알아보고 하기위해서 이렇게 기록으로 남기게 되었다.

이것저것 모든걸 다 사용해 볼순 없어서 상대적으로 많이 쓰이고 인기가있다는 Mocha에 대해서 알아보려고 한다.

* [Mocha](https://mochajs.org/)

공식문서를 보면 Mocha 는 Nodejs 와 브라우저에서 실행되는 기능이 풍부한 JavaScript test framework로 비동기테스트를 간단하고 재미있게 만들고 순차적으로 실행되므로 유연하고 정확한 보고가 가능하고 알수없는 예외를 올바른 테스트케이스에 매핑 할 수 있다고 한다.

일단 공식문서의 START 를 따라가본다.

```javascript
// 전역으로 설치
$ npm install mocha -g
$ mkdir mocha-test
```

mocha_test.js 파일을 하나 만들고

```javascript
// 공식문서에 있는 테스트코드
var assert = require('assert');
describe('Array', function() {
  describe('#indexOf()', function() {
    it('should return -1 when the value is not present', function() {
      assert.equal(-1, [1,2,3].indexOf(4));
    });
  });
});
```
* assert 모듈을 사용하기 위해 불러옵니다. assert 는  NodeJS에서 사용할 수 있는 테스트 모듈입니다.
* describe 는 중첩해서 사용이 가능하며 테스트 suite 를 만들때 사용하고 그안에 it() 으로 테스트 코드를 작성한다.
* it() 함수는 실제 테스트케이스를 작성하게되고 첫번째 인자로 테스트케이스의 설명을 쓰고 두번째 인자로 테스트코드를 콜백함수로 작성한다.
* 테스트예제를 보면 배열에 4가 없는데 indexOf 로 4를 찾는데 없으면 -1을 출력하게된다.
* 이 -1 결과값이 equal 의 첫번째 인자로 받은 -1과 같은지 비교하게된다.
* 해당루트에서 터미널을 키고 mocha 를 입력하면 테스트가 실행되고 

```javascript
Array
    #indexOf()
      √ should return -1 when the value is not present


  1 passing (7ms)
```

위와같은 테스트결과가 나온다. 분위기나 색상을 보아하니 성공한것같다.

저 테스트 코드를 틀린값이 나오도록 작성한다면?

```javascript
// 공식문서에 있는 테스트코드
var assert = require('assert');
describe('Array', function() {
  describe('#indexOf()', function() {
    it('should return -1 when the value is not present', function() {
      assert.equal(-1, [1,2,3,4].indexOf(4));
    });
  });
});
```

배열에 4를 추가하였다.

```javascript
 Array
    #indexOf()
      1) should return -1 when the value is not present


  0 passing (9ms)
  1 failing

  1) Array
       #indexOf()
         should return -1 when the value is not present:

      AssertionError [ERR_ASSERTION]: -1 == 3
      + expected - actual

      --1
      +3

      at Context.<anonymous> (test.js:5:14)
```
describe 에 작성한 설명은 정상적으로 출력되고 it의 첫번째 인자로받은 설명문 또한 정상적으로 나오고 이후 -1 == 3 이 다르다는 에러메시지를 출력한다.

전역이 아닌 프로젝트의 개발 의존성으로 설치하면
```javascript
$ npm install --save--dev mocha
// 터미널에서 실행문
$ ./node_modules/mocha/bin/mocha 
// pakage.json 테스트 스크립트 설정
"scripts": {
    "test": "./node_modules/mocha/bin/mocha $(find . -name '*.spec.js') --recursive -w"
  }
$ npm test 로 한번만 설정하면

// 파일이 변경될 때마다 자동으로 테스트가 실행됩니다.
```

**이중 콜백 에러**
```javascript
it('double done', function(done) {
  // Calling `done()` twice is an error
  setImmediate(done);
  setImmediate(done);
});
```

위의 예제는 함수 내부에서 중복으로 콜백을 사용했을 경우의 예제이다.

```javascript
 √ double done
  1) double done

  1 passing (8ms)
  1 failing

  1) double done:
     Error: done() called multiple times
```
첫번째 실행을 통과했지만 두번째 실행에서는 에러를 출력하게 된다.

위의 예제에서 NodeJS 의 내장된 assert 을 사용하여 테스트하였지만<br/>
Mocha 에서는 다양한 assert 라이브러리를 사용할 수 있다.

공식문서의 내용이 꽤많다... 우선 github에 업로드하기위해 오늘의 내용은 여기까지 정리하려고 한다.

# 181217

> React 에서 불변성이 중요한 이유는 무엇인가

> javascript 에서 Function 과 Arrow Function 의 차이점은 무엇인가



