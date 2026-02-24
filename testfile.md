어제 헷갈렸던 언리얼 엔진 에디터의 핵심 세 가지 요소는 다음과 같다.
레벨
컨트롤러
액터

언리얼 엔진의 게임 플레이 프레임 워크
AI 활용 설정
사진 설명을 입력하세요.

게임모드: 현재 게임이 어떤 규칙으로 들어갈지 정의
pawn 플레이어 혹은 AI가 조종할 수 있는 오브젝트
character: pawn을 상속한 인간형 오브젝트.
capsule collision, skeletal mesh, CharacterMovementComponent가 기본으로 들어있음.
동물의 경우 움직임 시스템에 따라 다르지만 보통 character.

레벨
게임이 진행되는 공간
언리얼 엔진에선 persistant level이라는 이름의 메인 레벨이 있고, 필요하면 sub-level을 만들어 불러올 수도 있음. 서브 레벨은 뭐랄까 일종의 레이어 같은 느낌인 것 같다. Load stream level (by name) 같은 블루프린트 써서 부를 수도 있다.
이런 기능은 보통 성능 이슈로 (최적화) 쓰인다고 한다.

controller와 pawn의 관계.
Possess하여 직접 제어
AI controller. behavior tree 등을 통해 의사결정 과정을 미리 구현

UMG (Unreal Motion Graphics)
언리얼에서 UI를 만드는 툴의 이름

액터: 레벨에 배치 가능한 모든 오브젝트.
액터의 life cycle 4단계 간단히 초기화→시작→tick→destroy
초기화: 생성. 레벨에 생성됐다는 뜻은 아니고 그냥 엔진 어딘가에.
시작: 맵 안에 들어옴
tick: 시작 후에 매 프레임마다 액터의 상태, 상호작용, 움직임 등 체크. destroy될 때까지 계속됨.
destroy: 특정 이벤트 생기거나 게임 종료 시점에.

Pawn, Character, 그리고 Component
Pawn: 액터를 상속받아 “조종 가능한” 특징을 더한 클래스
Character: Pawn을 상속받아 “걷기, 달리기, 점프”등의 이동 로직이 포함된 클래스
컴포넌트: 액터가 본체라면 컴포넌트는 액터에 붙이는 부품 개념.
컴포넌트는 액터의 기능임.
