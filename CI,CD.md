# CI/CD

어플리케이션 개발 단계부터 배포까지 자동화를 통해 조금 더 효율적이고 빠르게 사용자에게 빈번히 배포할 수 있도록 만드는 것을 말한다.

## Continuous Integration(지속적인 통합)

> 버그수정이나 새로만드는 기능들이 Main Repository에 주기적으로 build되고 test되어 merge되는 것.

1. 코드 변경사항을 주기적으로 빈번하게 merge해야 한다.
    - 최대한 작은 단위로 나누어 개발하고 통합해 나가는 것이 중요하다.
2. 통합을 위한 단계(빌드, 테스트, 머지)의 자동화.
    - 개발 생산성 향상
    - 문제점을 빠르게 발견
    - 버그 수정 용이
    - 코드 퀄리티 향상

## Continuous Delivery(지속적인 제공) / Continuous Deployment(지속적인 배포)

마지막 배포단계에서 어떻게하면 자동화 해서 배포를 만들수 있을지를 고민하는 단계

### Continuous Delivery

> CI를 통해서 주기적으로 merge된 코드의 변경사항들이 자동으로 build가 되고 test가 되었다면 배포하는 단계에서 배포할 Release과정(Prepare Release)을 거치고 준비된 Release가 문제가 없는지 개발자나 검증팀이 검증하고 배포해도 되겠다(Deploy Release)라고 한다면 수동적으로 배포하는 단계

### Continuous Deployment

> Release가 준비되자마자 자동으로 사용자에게 배포할 수 있도록 모든 과정을 자동화하는 것

## CI/CD PipeLine

> CODE -> BUILD -> TEST -> RELEASE -> DEPLOY

1. 개발자가 작은 단위로 기능을 나누어서 주기적으로 메인 리포지토리에 머지하면
2. 자동으로 빌드하고
3. 테스트과정을 거쳐서 
4. 릴리즈 준비를하고
5. 수동적(지속적인 제공), 자동적(지속적인 배포)으로 최종 배포