# 딥러닝 1일차

## 퍼셉트론

### 1. 퍼셉트론 정의

- 퍼셉트론은 여러개의 신호를 받아 하나의 출력값을 반환하는 것
- 신호는 전류 혹은 강물처럼 흐르는 이미지를 가진다.
- 퍼셉트론을 통해 정보가 앞으로 전달하는 것, 그러나 흐른다/안흐른다 (1 or 0) 값만 가진다.

a. 퍼셉트론 그림 예시

`![perceptron 사진](deep_learning01.assets/0*LJBO8UbtzK_SKMog.png)

`입력이 3개인 퍼셉트론`

- x1, x2, x3는 입력 신호, y는 출력 신호, w1, w2, w3은 가중치를 의미한다.
- 그림속의 원을 **뉴런** 혹은 **노드** 라고 불린다. 
- 입력신호 x들이 뉴론에 보내질 때 가중치가 곱해진다.
- 이 때, 뉴런에서 보내온 신호들 (x1*w1, x2*w2) 총합이 한계를 넘어설 때 1을 출력한다. -> 뉴런이 활성화
- 한계값을 **임계값** 혹은 **세타** 라고 불린다. 

b. 퍼셉트론 수식

![perceptron 수식](deep_learning01.assets/output-of-perceptron-mathematically2.jpg)

- 퍼셉트론은 각 신호에 고유한 가중치를 부여하는데, 각 신호가 주는 영향력을 기준으로 가중치 값이 달라진다. 
- 가중치가 클수록 더 중요함을 의미한다. 

### **2. 논리 회로**

#### a. AND, OR, XOR 게이트

![and gate image](deep_learning01.assets/bitwise_datasets.png)

- 입력 신호 및 출력 신호의 대응 표 -> **진리표**
- AND 게이트는 입력 값 두개가 모두 1일 때 출력값 1을 가진다. -> 임계값을 넘을 때를 의미
- OR 게이트는 입력 신호중 하나라도 1이 나오면 1을 출력하는 회로.
- XOR 게이트는 `배타적 논리합` -> **x1, x2 둘 중 하나가 1일 때만 1을 출력**
  - XOR 게이트는 퍼셉트론으로 구현 불가능: 그림으로 보다시피 직선**(선형)**으로 구역을 구분할 수 없기 때문이다. 
  - 선형이라는 제약을 없애면 곡선(비선형)으로 표현 가능핟. 
  - 아니면 차원을 하나 더 형성해서 단면을 자르는 이미지 (선형)을 생각하면 가능하다.

#### b. NAND 게이트

- NAND 게이트는 AND 게이트의 매개변수를 마이너스화 하면 된다. 

### 3. 다층 페셉트론

- 정의: 여러개의 층으로 구성되어 있는 퍼셉트론
- XOR 게이트를 구현하기 위한 방법
  - 기존 게이트 조합하기: AND, OR, NAND 게이트를 활용하여 조합하면 XOR 게이트 구현 가능하다. 
  - ![xor gate image](deep_learning01.assets/img.png)
  - 왼쪽 기준으로 부터 0, 1, 2층으로 불린다. 
- 다층 퍼셉트론 구동 원리: 
  - 0층의 두개의 뉴런이 입력 신호를 받아서 1층의 뉴런으로 신호를 보낸다.
  - 1층의 유런이 2층의 뉴런으로 신호를 보낸다. 그 다음 2층의 뉴런은 y를 출력한다.
  - XOR 게이트 -> `부품을 전달`

