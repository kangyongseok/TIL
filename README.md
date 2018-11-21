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