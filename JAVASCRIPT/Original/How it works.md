How it works. JavaScript는 어떻게 작동하는가

많은 사람들이 JavaScript를 사용하고 있다. 웹에서만 사용되던 JavaScript는 이젠 다양한 곳에서 사용된다. Electron을 이용하여 데스크탑 앱으로서 사용되기도 하고, React Native는 심지어 JavaScript를 이용하여 앱개발을 가능하게 한다. 하지만 이렇게 인기가 많아진 JavaScript가 어떻게 동작하지는 정작 알지 못하는 경우가 많다. 사실 필자도 이 글을 쓰기 전까지는 단순히 V8엔진에서 작동한다 이정도만 알고 있었다. 지금부터 이런 사람들을 위해서 JavaScript의 동작원리에 대해서 작성해보고자 한다.

우선 정말 간단히 설명하자면 위에서 말한 것과 같이 브라우저의 엔진이 작성한 JavaScript 파일을 컴파일하여 결과로서 보여주는 것이다. 하지만 이렇게 얕은 지식은 진짜 이해를 돕지는 못한다. 정말 깊게 알아보고자 한다면 웹이라는 강력한 플랫폼이 어떻게 존재하는지부터 설명하는 것이 옳은 것 같다. 웹은 자바스크립트가 가장 많이 사용되는 플랫폼이기 떄문이다.

브라우저의 작동원리
브라우저라는 것은 사실 모두 이미 알고있고 사용하고 있다. 지금 당장 이 글을 보고 있는 순간에도 크롬, 인터넷 익스플로어(IE), 엣지, 웨일 등의 다양한 브라우저를 통해서 보고 있을 것이다.

우선 JavaScript를 실제로 컴파일 시켜주는 V8엔진에 대해서 설명하겠다. V8엔진은 오픈소스 응용 프로그램 프레임워크이다. JavaScript를 바이트코드로 컴파일 하거나 인터프리트하는 대신 실행전 기계어로 컴파일하여 성능을 향상 시켰다. Chrome과 Node에서 사용중인 엔진이고 웹 브라우저 외에 다른 곳에서 독립적으로 실행하는 것도 가능하다. 이 엔진의 구성요소는 크게 Memory Heap과 Call Stack으로 나뉜다. Memory Heap은 메모리의 할당이 일어나는 곳이며 Call Stack은 코드 실행에 따라서 호출 스택이 쌓이는 곳을 의미한다. 이외에도  Callback queue와 Web API's 부분으로 나뉜다. JavaScript는 싱글스레드에서 작동된다. 이는 한번에 한 작업을 처리할 수 있다는 것을 의미한다. 따라서 당연히 하나의 호출 스택을 갖게되고 작업이 추가될 때마다 스택 프레임이 추가된다. 우리가 흔히 Exception(예외) 처리를 할때에 사용하는 stackTrace라는 것은 에러가 발생했을 때의 스택 프레임부터 하단까지 이어지는 것을 의미한다. 호출 스택이 하나만 존재하기에 주의해야할 점도 있다. 스택 프레임을 무한정 가용할 수 있는 것은 아니기 때문에 Call Stack의 가용치를 벗어날 경우에 에러를 발생시킨다.

어쩌면 이 글은 브라우저의 작동원리를 설명하고 있는 것인지도 모르겠다. 