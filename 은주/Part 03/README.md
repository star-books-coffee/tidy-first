# Part 03. 이론
- 이론을 이해하면 최적의 응용이 가능하다.
- 소프트웨어 설계에서 영원한 질문
  - 언제 소프트웨어 설계 결정을 시작해야 하나?
  - 언제 소프트웨어 설계 결정을 중단하고, 시스템 동작을 변경해야 하는가?
  - 다음 결정은 어떻게 내릴 것인가?
- 위 질문들은 그 시점에는 합리적으로 논리적인 답을 찾는데 **필요한 정보가 존재하지 않으므로** 당장 합리적이고 논리적으로 답할 수 없다
- 이론을 이해하면, 이러한 질문에 **추측으로 답해야 할 때를 대비해 판단력을 키울 수 있다**
  - 또한 논쟁을 좀 더 **건설적** 으로 할 수 있다
- 이론은 동료와의 견해 차이가 깊어질 때 도움이 된다
  - 서로 다른 목표를 달성하려고 할 때도, **이론적 틀을 공유** 하는 것이 유용하다
  - 원칙에 동의하지 않아도 **서로의 원칙에 대해 논의** 할 수 있다면 더 빨리 합의할 수 있고, 배울 수 있는 기회가 있다

### Chapter 22. 요소들을 유익하게 관계 맺는 일
- 소프트웨어 설계 : 요소들을, 유익하게, 관계 맺는 일
- 설계르 구성하는 요소들과 그들의 관계, 관계에서 파생되는 `이점`이 바로 설계이다
- 시스템의 구조
  - 요소 계층 구조
  - 요소 사이의 관계
  - 이러한 관계가 만들어내는 이점

### Chapter 23. 구조와 동작
- 소프트웨어가 가치를 만드는 2가지 방식
  - 현재 소프트웨어가 `하는 일`
  - 미래에 새로운 일을 시킬 수 있는 `가능성`
- 특정 방식으로 동작하는 시스템이 있다는 것만으로도, 시스템이 어떻게 동작해야 하는지에 대한 욕구가 달라진다
- 시스템을 더 가치 있게 만들기 위해서는 **다음에 무엇을 할 수 있는지에 대한 선택 기회를 만들면 된다**
- **구조는 미래의 기회를 만든다**
- 구조 변경, 동작 변경은 모두 가치를 만들지만 근본적으로 다르다.
  - 구조 변경은 가역성이 있지만, 동작 변경은 없다. (되돌릴 수 있는 능력)

### Chapter 26. 옵션
- "다음에 어떤 동작을 구현할 수 있을까?" 라는 질문은 동작 후보 목록이 많을 수록 가치 있따
- 목록 규모를 늘릴 수 있다면 가치를 창출한 것이다
- 가치에 대한 예측이 불확실할수록 바로 구현하는 것보다 옵션이 지닌 가치가 크다
- 소프트웨어 설계는 **변화를 위한 준비로, 동작 변경에 대한 준비** 이다
- 오늘 우리가 하는 설계는 내일의 동작 변경을 '구매' 하는 '옵션' 에 대해 지불하는 프리미엄이다.

### Chapter 27. 옵션과 현금흐름 비교
- 확실히 코드 정리부터 해야 할 때
  - 비용 (코드정리) + 비용 (코드정리 후 동작 변경) < 비용 (바로 동작 변경)
- 소프트웨어 설계의 시기와 범위에 영향을 미치는 인센티브를 인식하는데 익숙해지자
  - 그러면 중요한 순간에 언제, 어떻게 설계해야 하고 언제 설계하지 말아야 하는지 직감적으로 알 수 있게 된다

### Chapter 28. 되돌릴 수 있는 구조 변경
- 대부분 소프트웨어 설계 결정은 쉽게 되돌릴 수 있다
  - 동작 변경을 쉽게 할 수 있지만, 부작용도 크지 않다
- 되돌릴 수 없는 설계 변경의 예시로는 서비스로 추출하기가 있다
- 되돌릴 수 있었떤 설계 결정이 되돌릴 수 없게 되는 시나리오는 **설계 결정이 코드베이스 전체에 전파될 때** 이다
  - 확산될 가능성이 있는 결정인지 생각해보고, 
  - 그런 일이 발생할 경우 한번에 하나씩 정리해나가자

### Chapter 29. 결합도
- 결합도가 의미를 지니려면, **어떤 변경사항과 결합되어 있는지** 말해야 한다
  - 두 요소가 결코 일어나지 않는 변화와 결합되어 있다면, 우리가 관심가질 필요가 없다
- 결합도 분석은 프로그램 소스코드 보는 것만으로는 부족하다
  - 어떤 변경이 발생했거나, 발생할 가능성이 있는지 알아야 한다
- 결합도는 **소프트웨어 비용을 결정** 한다
- 결합도를 주목하는 이유는 2가지 성질 때문이다
  - 일대다 : 어떤 변경 발생 시 한 요소는 여러 요소와 결합이 일어난다
  - 연쇄작용 : 연쇄적인 변경
- 시스템이 복잡하다는 것은 **변화가 예상치 못한 결과를 초래한다**는 의미이다

### Chapter 30. 콘스탄틴의 등가성
- 소프트웨어 설계의 목표는 **소프트웨어 비용을 최소화**하는 것이다
- 실제 사용으로부터 피드백을 빨리 얻을 수록 중요하지 않은 행동에 소비하는 시간/비용/기회를 줄일 수 있다
- 소프트웨어 비용은 **그것을 변경하는 데 드는 비용과 거의 같다**
- 가장 비용이 많이 드는 하나의 변경이 나머지 변경을 모두 합친 것보다 더 많은 비용이 든다
  - 변경 비용은 큰 변경들의 비용과 거의 같다는 뜻이다
- **결합도가 변경을 전파한다**

### Chatper 31. 결합도와 결합도 제거
- 직접 마주치기 전에는 무의식적으로 자신이 어떻게 결합도를 가정하고 있는지 스스로 알기 어렵다
- 한 종류의 코드 변경에 대한 결합도를 줄일수록, 다른 종류의 코드 변경에 대한 결합도가 커진다
  - 따라서 모든 결합을 색출하듯 없애려고 애쓰지 말아야 한다

### Chapter 32. 응집도
- 결합된 요소를 자체 `하위 요소` 로 묶자
  - 하위 모듈은 요소들이 결합되어 있기에 응집도가 있따
- 도우미 함수를 추출하는 것은 일종의 **응집도가 있는 하위 요소 추출** 접근 방식이다
  - 응집도가 있으면, 분석 및 변경이 쉽고, 우발적 동작 변경에 대한 가능성이 줄어든다
- 모든 것을 급격히 재배치하지 말고 한번에 한 요소씩 이동하자
- 모두가 스카우트 규칙 (찾았을 때보다 더 나은 상태로 남겨두라) 을 따르면 시간이 지날수록 더 좋은 코드가 될 것이다

### Chapter 33. 결론
- 코드정리가 먼저인가? 라는 질문에 영향을 주는 4가지
  - 비용
    - 코드 정리하면 비용이 줄어들까
    - 나중에 하는 편이 나을까
    - 줄일 가능성이 있을까
  - 수익
    - 코드를 정리하면 수익이 더 커질까
    - 더 빨리 수익이 발생할까
    - 수익이 더 커질 가능성이 있을까
  - 결합도
    - 코드를 정리하면 변경에 필요한 요소 수가 줄어들까
  - 응집도
    - 코드를 정리하면 변경을 더 작고 좁은 범위로 집중시켜 더 적은 수의 요소만 다룰 수 있을까