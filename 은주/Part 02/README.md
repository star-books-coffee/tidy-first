# Part 02. 관리
- `코드 정리` : 코드의 구조를 변경하는 것
### Chapter 16. 코드 정리 구분
- **코드 정리는 별도의 PR 로 만들고, 가급적 PR 당 몇 개의 코드정리만 넣자**
- 코드 정리와 동작 변경을 번갈아가며 전환할 때마다 새 PR 을 열어야 한다.
  - PR을 나눌지, 1개의 PR 로 처리할지는 장단점이 극명하다.
  - 나눌 경우 : 검토 시간 단축으로 환영 받지만, 무시될 우려가 있음
  - 나누지 않을 경우 : 전체 흐름을 파악할 수 있지만, 유용한 피드백을 제공하기 너무 큰 덩어리일 수 있음

### Chapter 18. 코드 정리의 일괄 처리량
- 일괄 처리 코드 정리 작업이 많을 수록
  - `충돌`: 코드 병합 과정에서 충돌할 가능성이 커지며, 작업 병합 비용도 크게 증가한다
  - `상호작용` : 코드 정리 사이에 동작 변경이 잇으면 병합 비용은 급격히 증가한다
  - `추측` : 다음 동작 변경에 도움 될 만큼만 코드 정리하는 것이 좋다
- 이러한 3가지 요인으로 인해, 보통 한번에 처리하는 코드 정리 개수를 줄이고, 일괄로 처리한다.
- 하지만 하나의 변경 사항을 검토하고 배포하는 데 드는 고정 비용 자체가 상당히 많이 들기 때문에, 일괄 처리 대신 다른 방식을 선택할 수 있다.
- 코드 정리 비용을 줄이고자 한다면, **코드 정리 개수를 늘려서 동작 변경에 소요되는 비용을 줄이라. 그러면 검토 비용도 줄어든다**

### Chapter 19. 리듬
- 한번의 코드 정리에 1시간 이상이 걸리면, 원하는 동작 변경을 위해 필요한 최소한의 구조 변경 시기를 놓쳤다는 의미일 수 있다
- 동작 변경에 앞서 코드 정리를 선행하는 것이 더 유리할 수도 있다

### Chapter 20. 얽힘 풀기
- 정리한 코드와 변경할 동작이 얽혀 버린 경우 액션아이템 3가지
    1. 그대로 배포 (리뷰어들의 불편이 증가하고, 오류 발생 쉽지만 당장 처리 가능)
    2. 코드 정리, 변경 사항을 별도의 PR 이나 커밋으로 나눈다 (리뷰어들의 불편은 1번보다 덜하지만 작업 횟수는 늘어남)
    3. 진행중인 작업을 버리고, 코드 정리를 선행하는 순서로 다시 시작 (작업은 많아지지만, `이어지는 커밋과의 일관성은 분명`)
- 3번 케이스가 가장 좋다
- 우리가 작성하는 코드는 컴퓨터에 지시할 뿐만 아니라, 컴퓨터에 지시하려는 **의도를 사람들에게도 설명해야 하기 때문이다**
  - 컴퓨터에 지시만 하는 빠른 수행이 최종 목표가 되는 것은 아니다

### Chapter 21. 코드 정리 시점
- 코드 정리를 먼저 해두면 나중에 시스템 동작 변경을 더 쉽게 한다
  - 보편적 영역을 정리하는 것만으로 향후 변경을 단순화하는 가치가 창출된다
- 코드 정리는 설계한 세부결과를 깨달을 수 있는 방법이자, 생각할 수 있는 설계를 비춰준다
- 일반적으로 코드 정리를 먼저 하는 것을 선호하지만, 정리 그 자체를 목적으로 삼지 않도록 경계해야 한다.
- 요약
  - 코드 정리를 추천하지 않는 경우
    - 다시는 코드 변경이 없을 경우
    - 설계를 개선해도 더 쉬워지지 않을 경우
  - 나중으로 정리를 미루는 경우
    - 정리할 코드 분량이 많은데 보상이 바로 보이지 않을 때
    - 코드 정리에 대한 보상이 잠재적일 때
    - 작은 묶음으로 여러 번 나눠서 코드 정리가 가능할 때
  - 동작 변경 후 코드 정리하는 경우
    - 방금 고친 코드를 다시 변경할 예정일 때
    - 지금 정리하는 것이 더 저렴할 때
    - 코드 정리하는 데 드는 시간이 동작 변경에 드는 시간과 거의 비슷할 때
  - 코드 정리 후 동작 변경하는 경우
    - 코드 정리했을 때, 코드 이해가 쉽거나 동작 변경이 쉬워지는 즉각적 효과를 얻을 수 있을 때
    - 어떤 코드를 어떻게 정리해야 할 지 알고 있을 때