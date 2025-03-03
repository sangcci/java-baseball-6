# 설계
### 협력(도메인) 정의
“3자리 숫자를 맞추는 게임”

### 동작 순서
1. 사용자는 3자리 수를 입력한다.
    1. 만일, 잘못된 값을 입력할 경우 `IllegalArgumentException`을 발생시키고 어플리케이션을 종료한다.
2. 컴퓨터는 3자리 서로 다른 임의의 숫자를 생성한다.
3. 사용자의 값과 컴퓨터의 값을 비교한 후 결과를 출력한다.
    1. 스트라이크, 볼, 낫싱을 판단한다.
    2. 컴퓨터의 수를 맞출 때 까지(3스트라이크) 반복한다.
4. 컴퓨터의 값을 모두 맞출 경우, 게임 종료 문구와 함께 게임을 종료한다.
5. 게임 다시 시작 여부를 입력한다.
    1. 다시 시작할 경우 3번 과정으로 되돌아가고, 종료할 시 게임을 완전히 종료한다.

### 객체 설계
- `View`
    - `InputView` : Console 입력 받기
    - `OutputView` : Console 출력 하기
- `Controller`
    - `GameController` : 게임 시작하기, 다시 시작 여부 묻기
- `Model`
    - `Pitcher` : 숫자 생성
    - `Umpire` : 스트라이크 및 볼 판단
    - `RestartState` : 다시 시작 여부 판단
    - VO
      - `BaseballNumber` : 3자리 숫자 검증 및 전달