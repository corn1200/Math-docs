# Math-docs

# 목차
* [1. 벡터와 스칼라](#1-벡터와-스칼라)
    * [1.1. 벡터의 연산](#11-벡터의-연산)
    * [1.2. 벡터의 내적과 외적](#12-벡터의-내적과-외적)
* [2. 좌표계](#2-좌표계)
* [3. 피타고라스 정리](#3-피타고라스-정리)
* [4. 삼각비](#4-삼각비)
* [5. 삼각함수](#5-삼각함수)

# 1. 벡터와 스칼라
## 벡터(vector)
- 기하학적으로 벡터를 방향을 가진 선분 즉, 화살표로 표현한다.
- 벡터의 속성은 '길이(혹은 크기)'와 '가리키는 방향'
- '위치'는 벡터의 속성이 아니다.    
따라서 다른 위치에 있더라도 동일한 길이와 방향을 가리키는 두 개의 벡터는 동일한 것으로 취급된다.    
예를 들어, 아래의 그림에서 벡터 u와 v는 동일하다.
- 크기와 방향을 모두 갖는 물리량을 모델링하는 데 유용하다.  
ex) 빛이 비추는 방향, 다각형의 방향, 3D 세계에서의 카메라가 보고 있는 방향 등

![벡터](/img/vector0.png)

보통 벡터를 표시할 때는 굵은 소문자를 이용하지만 굵은 대문자를 이용하는 경우도 있다.    
다음은 각각 2차원, 3차원, 4차원 벡터의 표시 예이다.     
혹은 화살표를 사용하여 표기하기도 한다: $\overrightarrow{a}$    
$u = (u_x, u_y), N = (N_x, N_y, N_z), c = (c_x, c_y, c_z, c_w)$

### 벡터의 크기 계산
기하학적으로 벡터의 크기는 방향을 가진 선분의 길이이다.     
벡터의 성분이 주어졌다고 할 때, 다음과 같은 식을 이용해 벡터의 크기를 대수학적으로 계산해낼 수 있다.    
$||u|| = \sqrt{u_x^2 + u_y^2 + u_z^2}$

ex) $u = (1,2,3)$과 $v = (1,1)$ 벡터의 크기를 구하라.   
$||u|| = \sqrt{1^2 + 2^2 + 3^2} = \sqrt{1 + 4 + 9} = \sqrt{14}$

![벡터](/img/vector1.png)

마찬가지로, 위의 식을 2차원으로 일반화하면 다음과 같이 $v$를 얻을 수 있다.  
$||v|| = \sqrt{1^2 + 1^2} = \sqrt{2}$

![벡터](/img/vector2.png)   
연관 내용: 피타고라스의 정리

### 영 벡터와 단위 벡터
영 벡터란 모든 성분에 0을 가진 것이다.  
영 벡터는 굵은 0으로 표시된다: $0 = (0, 0, 0)$

단위 벡터란 크기가 1인 벡터이다.    
곱셈에서, $1 * n = n$일 때 n에 어떤 수를 넣더라도 항상 n이 나오도록 하는 1을 곱셈에서의 항등수라고 한다.    
벡터에서도 값과 벡터가 곱해질 때 단위 벡터는 항등수에 해당한다. 
단위 벡터는 크기가 1이고 방향을 가지고 있으므로, 여기에 값을 곱해주면 방향은 같지만 크기가 다른 벡터를 마음대로 만들 수 있다.   
혹은 크기는 무시하고 방향만 나타내기 위해서 사용한다.

모든 벡터는 정규화(normalize) 과정을 거쳐 단위 벡터로 만들 수 있다.     
단위 벡터의 용도는 일반적으로 회전의 중심축으로써 사용되는 경우가 많다.     
그 외에도 삼각형면의 법선 벡터(normal vector) 역시 단위 벡터를 사용한다.    
법선 벡터란, 평면에 수직인 벡터이다.

![벡터](/img/vector3.png)

### 벡터의 정규화
벡터의 정규화란 벡터의 크기를 1로 만들어 단위 벡터가 되도록 하는 것이다.    
다음과 같이 벡터의 각 성분을 벡터의 크기로 나누면 정규화가 된다.    
단위 벡터는 위에 모자를 씌워 표기한다: $\hat{u}$    
$\hat{u} = \frac{u}{||u||} = (\frac{u_x}{||u||}, \frac{u_y}{||u||}, \frac{u_z}{||u||})$

ex) $u = (1,2,3)$ 벡터를 정규화하라.    
$\hat{u} = \frac{u}{\sqrt{14}} = (\frac{1}{\sqrt{14}}, \frac{2}{\sqrt{14}}, \frac{3}{\sqrt{14}})$

## 스칼라(scalar)
- 크기와 방향을 가지는 벡터의 대비되는 개념
- 단지 크기만 있는 물리량이다.
- 좌표계가 변환되어도 그에 따라 변화하지 않는 양, 단순히 '하나의 숫자'이다.

### 벡터와 스칼라의 연산
스칼라는 벡터와의 곱셈 연산을 통해 벡터의 크기를 조정하는 데 사용된다.  
스칼라 연산은 벡터의 방향에는 영향을 미치지 않으며 단지 벡터의 크기만을 바꿀 뿐이다.    
각 항에 스칼라를 곱해주면 된다.     
만약 음수를 이용하는 경우에는 벡터의 방향이 뒤집힌다.   
즉, 벡터에서 부호는 방향을 결정하는 역할을 한다.    
$ku = (ku_x, ku_y, ku_z)$

![벡터](/img/vector4.png)

게임에서 캐릭터를 이동시킬 때, 단위 벡터와 스칼라의 곱을 사용한다.  
캐릭터를 이동시킬 방향(단위 벡터)에 이동하고자 하는 거리(스칼라) 값을 곱하면, 캐릭터가 이동할 벡터를 구할 수 있다.

즉, 캐릭터의 위치 벡터에 이동 벡터를 더하여, 최종적으로 캐릭터가 이동될 위치를 구해 캐릭터를 그 위치로 이동시키면 된다.

![벡터](/img/vector5.png)

### 역벡터
역벡터란 크기는 같으나 방향이 서로 반대인 벡터를 말한다.    
역벡터는 벡터 앞에 -(음부호)를 붙여서 표시를 한다.  
-(음부호)의 역할은 벡터의 방향을 바꾸는 역할을 하며, 각 성분에 -1을 곱한 것과 같다.     
예를 들어 (1, 1) 벡터에 -1을 곱해주면 크기는 그대로지만 방향이 반대가 된다는 것을 아래 그림을 통해 알 수 있다.

![벡터](/img/vector6.png)

# 1.1. 벡터의 연산
### 벡터의 덧셈
대응되는 성분을 더하면 두 개의 벡터를 더할 수 있다.     
이때, 더하고자 하는 벡터는 반드시 동일한 차원을 가져야 한다.    
교환법칙과 결합법칙이 성립한다.     
$u + v = (u_x + v_x, u_y + v_y, u_z + v_z)

교환법칙 성립: $u + v = v + u$      
결합법칙 성립: $(u + v) + w = u + (v + w)$

아래의 그림은 벡터의 덧셈의 기하학적 보간을 보여준다.

![벡터](/img/vector7.png)

### 벡터의 뺄셈
벡터의 덧셈과 비슷하게 벡터의 대응되는 성분을 빼는 방법으로 벡터의 뺄셈을 수행할 수 있다.   
벡터는 반드시 동일한 차원을 가져야 한다.    
$u - v = u + (-v) = (u_x - v_x, u_y - v_y, u_z - v_z)$

아래의 그림은 벡터 뺄셈의 기하학적 보간을 보여주고 있다.    
게임에서는 '내'가 '타겟'을 보는 방향을 구하고자 할 때 벡터의 뺄셈이 유용하게 사용된다.

![벡터](/img/vector8.png)

### 벡터의 분해
하나의 벡터는 두 개의 성분 벡터로 분해될 수 있다.

![벡터](/img/vector9.png)

위 그림에서 벡터 A는 벡터 B와 벡터 C의 합으로 분해되어진다.     
벡터 B와 벡터 C의 합이 결국 A 벡터이기 때문이다.

이렇게 벡터를 성분 분해하는 이유는 벡터 연산을 좀 더 효율적이고 쉽게 하기 위함이다.     
예를 들어 2차원 벡터끼리 연산을 할 때 각 벡터를 x, y 축의 두 성분 벡터로 분해하여 연산하면 다음과 같다.

![벡터](/img/vector10.png)

벡터의 연산이 복잡해질 수록 벡터 분해에 대한 이해는 필수적이다.         
벡터 내적의 이해와도 관련되어 있다.

# 1.2. 벡터의 내적과 외적
## 내적
- 내적은 벡터 대수학에서 정의하는 두 가지 곱셈 중 하나이다.
- 두 벡터 사이의 연산이지만, 내적의 결과는 벡터가 아닌 스칼라 값이다.
- 벡터의 내적을 구하는 공식은 다음과 같다.

1. $u * v = u_xv_x + u_yv_y + u_zv_z$
2. $u * v = ||u||||v|| \cos \theta$

1번은 두 벡터의 각은 모르고 벡터의 성분만을 알고 있을 경우 사용할 수 있는 공식이며, 2번은 두 벡터의 각과 크기를 알고 있을 경우 사용할 수 있는 공식이다.

1번의 식은 분명한 기하학적 의미를 보여주고 있지 않다.   
코사인 법칙을 이용하면 $u * v = ||u||||v||$의 관계를 발견할 수 있으며, 이는 두 벡터 간의 내적이 벡터 크기 배율을 가진 벡터 간 각도의 코사인임을 알 수 있다.

1번 공식을 2차원 벡터를 예로 들어 그림으로 표현하면 다음과 같다.

![벡터](/img/vector11.png)

2번 공식을 2차원 벡터를 예로 들어 그림으로 표현하면 다음과 같다.

![벡터](/img/vector12.png)

벡터 D의 크기는 A 벡터의 크기에 $\cos \theta$를 곱한 것이다.    
$||D|| = ||A|| * \cos \theta$   
여기서 A의 크기가 아닌, A를 분해한 벡터 D의 크기를 곱해주는 이유는 B 벡터에 실제로 영향을 주는 벡터가 D이기 때문이다.   
한편 벡터 C는 벡터 B의 방향으로 어떤 영향도 주지 못하기 때문에, 내적 계산에서 무시한다.

### 내적의 특성
$u$와 $v$가 모두 단위 벡터인 경우 $u * v$는 두 벡터 간 각도의 코사인이 된다.

![벡터](/img/vector13.png)

만약 $u * v = 0$ 이라면, 두 벡터는 직각이다.     
만약 $u * v > 0$ 이라면, 두 벡터 간의 각도 $\theta$는 90도($\frac{\pi}{2}$) 보다 작다.      
만약 $u * v < 0$ 이라면, 두 벡터 간의 각도 $\theta$는 90도($\frac{\pi}{2}$) 보다 크다.

![벡터](/img/vector14.png)

또한, 자기자신과 내적하면 자기자신 크기만큼의 제곱이다.     
자기자신과 이루는 각도는 0도 이며, $\cos 0 = 1$이기 때문에 결과적으로 같은 벡터 2개를 내적하면 제곱이다.

### 벡터의 내적 활용
첫째, 두 벡터 사이각을 내적을 통해 구할 수 있다.    
두 벡터의 성분을 알고 있다면, 크기를 알 수 있고 내적 계산을 이용해 $\arccos \theta$를 통해 구할 수 있다.
$$\cos \theta = \frac{a * b}{||a||||b||} = \frac{a_xb_x + a_yb_y + a_zb_z}{||a||||b||}$$
$$\theta = \arccos(\frac{a * b}{||a||||b||})$$

![벡터](/img/vector15.png)

둘째, 어떤 벡터 a에서 수직으로 내린 길이(투영 길이)를 구할 때 내적을 사용한다.

![벡터](/img/vector16.png)

위의 그림에서 벡터 a의 투영 길이를 구하고자 할 때는 벡터 b의 단위 벡터를 이용한다.  
벡터 b의 단위 벡터의 길이는 1이며 내적 공식에 적용하면 $a * b = ||a|| * 1 * \cos \theta$가 되어 결국 투영 길이는 $||a|| \cos \theta$가 된다.   
또는 $a_xb_x + a_yb_y + a_zb_z$에서 벡터 b의 단위 벡터를 적용하면 된다.     
투영 길이는 곧 벡터 b의 방향으로 얼마만큼 뻗어있는지 그 정도(크기)를 의미한다.

셋째, '나'의 방향 벡터가 있을 때 적이 주인공의 앞에 있는지 뒤에 있는지 판단할 때 사용된다.      
적의 위치에서 '나'의 위치를 뺀 벡터 즉, 내가 적을 바라보는 방향 벡터와 나의 Forward 벡터 간 내적을 했을 때, 각이 -90도 ~ 90도 사이에 있으면($\cos \theta$가 양수이면) 적이 나의 앞에 있는 것이고, 각이 90도 ~ 270도 사이에 있으면($\cos \theta$가 음수이면) 적이 나의 뒤에 있는 것이다.

![벡터](/img/vector17.png)

넷째, 적이 '나'의 시야각 안에 들어와 있는지 아닌지 판단할 때 사용된다.    
'나'의 시야각을 $\theta$라고 하면, Forward 벡터와 적과 '적의 위치에서 나의 위치를 뺀' 벡터 A 간의 내적을 통해 나오는 각도 값이 $\frac{\theta}{2}$를 넘지 않아야 시야각 내에 존재한다는 것을 판별할 수 있다.

![벡터](/img/vector18.png)

다섯째, 점 A와 평면 S 간의 최단 거리를 구할 때 내적을 이용해 구할 수 있다.  
(B는 평면 위의 점, d는 점 A와 평면 S 간의 최단 거리)    
$(A - B) * n = d$

![벡터](/img/vector19.png)

단면으로 표현하면 아래와 같다.

![벡터](/img/vector20.png)

벡터 BA와 평면의 법선 벡터(normal vector)와 내적을 구하면, $||BA|| * \cos \theta$값이 된다.     
이때, 평면의 법선 벡터는 정규화된 단위 벡터라고 가정한다.   
'투영 길이'를 떠올려보면 점 A와 평면 S 간의 최단거리 d가 됨을 알 수 있다.   
만약, 거리값이 0이면 A는 평면 위의 점이 된다.

## 외적
- 벡터 수학이 정의하는 두번째 형식의 곱은 외적이다.
- 스칼라로 계산되는 내적과는 달리, 외적의 결과는 또 다른 벡터이다.
- a와 b 두 벡터의 외적을 수행하면 다른 벡터 p를 얻으며, 이는 a와 b에 서로 지각을 이룬다.    
즉, p는 a에 직각이며, p는 b에 직각이다.
- 벡터의 외적을 구하는 공식은 다음과 같다.

1. $p = a * b = \hat{n}||a||||b|| \sin \theta$
2. $p = a * b = [(a_yb_z - a_zb_y), (a_zb_x - a_xb_z), (a_xb_y - a_yb_x)]$

1번의 식을 자세히 살펴보면, n은 방향 벡터이고, 나머지는 값이기에 결과는 벡터라는 것을 알 수 있다.   
또한, 외적 벡터의 크기는 두 벡터의 크기에 $\sin \theta$를 곱한 값과 같음을 알 수 있다.

![벡터](/img/vector21.png)

2번의 식은 다음과 같이 행렬식(Determinant)를 이용하여 간단히 쓸 수 있다.    
($i = (1,0,0), j = (0,1,0), k = (0,0,1)$)

![벡터](/img/vector22.svg)

$a * b$ 외적 벡터의 방향은 수학에서는 오른손 좌표계를 사용하며, 게임은 엔진이 사용하는 좌표계에 따라 다르다. (OpenGL에서는 오른손 좌표계, Unity나 Direct3D에서는 왼손 좌표계)   
예를 들어, Direct3D는 왼손 좌표계를 사용하므로 왼손법칙에 따라 외적 벡터의 방향을 계산하지 않고도 알 수 있다.   
왼손으로 첫번째 벡터 방향으로 손바닥을 맞춘 후, 두번째 벡터 방향으로 구부렸을 때 엄지 손가락이 가리키는 방향이 바로 외적으로 리턴되는 벡터의 방향이 된다.

![벡터](/img/vector23.png)

### 외적의 특성
- 외적의 결과는 내적과 달리 벡터이기 때문에 방향과 크기를 동시에 가지게 된다.   
방향: $u \times v \perp u$ 이고 $u \times v \perp v$ 이다. 즉, 두 벡터 $u$와 $v$ 에 동시에 수직이다.    
크기: 외적 벡터의 크기는 $u$ 와 $v$를 변으로 하는 평행사변형의 넓이이다.

![벡터](/img/vector24.png)

외적도 내적과 마찬가지로 주로 단위 벡터와 함께 사용되는데, 예를 들어 위의 그림에서 u와 v가 단위 벡터라면, u와 v의 외적 결과값인 벡터 p의 크기로 u와 v의 사이각을 판단할 수 있다.    
벡터 p의 크기가 1이라면 u와 v를 연결해서 만든 도형이 가로세로가 1인 정사각형임을 알 수 있고, 결국 벡터 u와 벡터 v가 수직임을 알 수 있다.

- 내적과 달리 교환 법칙이 성립하지 않으며, 순서를 바꾸면 반대 방향의 벡터가 나온다: $u \times v = -(u \times v)$
- 내적과 동일하게 분배 법칙은 성립한다: $u \times (v + w) = (u \times v) + (u \times w)$
- 두 벡터가 모두 영벡터가 아닐 때, $u \times v = 0$인 것은 $u$와 $v$가 서로 평행인 것과 동치이다.   
즉, 두 벡터가 평행하면 크기는 0이다. $(\sin \theta = 0)$

![벡터](/img/vector25.png)

### 벡터의 외적 활용
첫째, 평면의 법선 벡터를 구할 때 사용한다.  
삼각형의 세 점을 알고 있다고 할 때, 벡터 2개를 구할 수 있게 되고 그 두 벡터를 외적하면 해당 삼각형이 속한 평면의 법선 벡터를 구할 수 있다.

![벡터](/img/vector26.png)

입체적으로 표현하면 아래 그림과 같다.

![벡터](/img/vector27.png)

또한, 삼각형의 넓이를 구할 때도 외적을 사용할 수 있다.

![벡터](/img/vector28.png)

둘째, 평면이 앞면인지 뒷면인지를 알아낼 수 있고, 따라서 컬링(culling)할 때 사용된다.    
법선 벡터가 한 평면의 뒤를 가리킨다면, 뒷면을 화면 출력에서 제외되는 면이 된다.     
이와 같이 보이지 않는 뒷면을 화면 출력에서 제외시키는 것을 백페이스 컬링(backface culling)이라고 하며, Direct3D에서는 컬링 옵션에 따라 출력에서 제외시키거나 출력하게 할 수 있다.   
컬링의 기준이 되는 것이 바로 이 법선 벡터의 방향이다.   
eye 벡터와 평면의 법선 벡터의 내적으로부터 얻는 $\cos \theta$ 값을 사용하면 앞과 뒤를 판단할 수 있다.

![벡터](/img/vector29.png)

셋째, 점과 직선사이의 거리를 구할 때 사용된다.

![벡터](/img/vector30.png)

직선 S의 위의 점 B와 C를 임의로 선택한다.   
$BA$ 와 $BC$ 벡터를 만들어, 평행사변형의 높이를 구하는 방법을 응용해 문제를 풀 수 있다.

넷째, 빛의 방향과 평면의 법선 사이의 각도를 이용해 평면에 적용될 빛의 영향을 결정하게 된다.     
만약 빛을 평면에 비추고 싶다면, 평면을 이루는 각 벡터 정보에는 법선 벡터에 대한 정보가 반드시 있어야한다.

# 2. 좌표계
좌표계는 크게 2D 좌표계와 3D 좌표계로 나눌 수 있다.     
2D 좌표계는 모니터 좌표계와 동일하며 x, y 좌표를 가진다.    
3D 좌표계는 공간상의 한 점을 나타내기 위해 x, y, z 좌표로 위치를 나타낸다.  
3D 프로그래밍은 3D 좌표계를 사용하며 Direct3D는 3D 공간상의 정점들을 2D 좌표계로 바꾸어 출력하게 된다.  

### 왼손 좌표계 & 오른손 좌표계
두 좌표계의 차이는 +z축이 진행하는 방향에 있다.     
왼손 좌표계에서의 +z축은 화면 안쪽으로 향하며, 오른손 좌표계에서는 화면 바깥쪽으로 향한다.  
Direct3D와 Unity3D는 왼손좌표계를 사용한다.

![좌표계](/img/coordinate0.png)

2차원에서 도형은 한 점(원점 또는 임의의 위치)을 기준으로 회전된다.  
하지만 3차원에서는 하나의 축(x, y, z축 혹은 임의의 축)을 기준으로 개체가 회전된다.

왼손 좌표계에서 회전 방향은 각 축에 대해 시계방향(clockwise)이다.   
왼주먹을 말아쥐고 엄지를 들었을 때 엄지방향이 회전축 방향, 말아쥔 손가락 방향이 회전방향임을 알 수 있다.

오른손 좌표계에서 회전 방향은 각 축에 대해 반시계방향(counterclockwise)이다.    
오른주먹을 말아쥐고 엄지를 들었을 때 엄지방향이 회전축 방향, 말아쥔 손가락 방향이 회전방향임을 알 수 있다.

![좌표계](/img/coordinate1.png)

# 3. 피타고라스 정리

![피타고라스](/img/pytha0.svg)      
$a^2 + b^2 = c^2$   
직각삼각형에서 빗변의 길이의 제곱은 나머지 두 변의 길이를 제곱한 뒤 더한 것과 같다.

직각삼각형의 세 변의 길이를 각각 a, b, c 라 하고 변 a, b 사이 각도가 직각을 이룰 때, 즉 변 c가 빗변일때 $a^2 + b^2 = c^2$가 성립함을 뜻한다.

### 유클리드의 증명법

![피타고라스](/img/pytha1.gif)

위의 그림과 같이 $\angle C = 90^\circ$인 직각삼각형 ABC 에 대하여 세 변의 길이를 각각 한 변의 길이로 하는 정사각형 ADEB, ACHI, BFGC를 그린다.   
점 C에서 변 AB에 내린 수선의 발을 M, 그 연장선과 변 DE와 만나는 점을 N이라고 하자.      
이 때   
1. $\Box ACHI = 2 \triangle ACI$   

또, 밑변의 길이와 높이가 각각 같으므로,     

2. $\triangle ACI = \triangle ABI$

두 변의 길이와 그 끼인각의 크기가 각각 같으므로,    

3. $\triangle ABI \equiv \triangle ADC$    

밑변의 길이와 높이가 각각 같으므로,     

4. $\triangle ADC = \triangle ADM$     
5. $\Box ADNM = 2 \triangle ADM$   

(1), (2), (3), (4), (5)에서     

6. $\Box ACHI = \Box ADNM$  

같은 방법으로

7. $\Box ACHI = \Box ADNM$

(6), (7)에서    
$\Box ADEB = \Box ACHI + \Box BFGC$     
$\therefore \overline{AB}^2 = \overline{BC}^2 + \overline{BC}^2$

### 바스카라의 증명법

![피타고라스](/img/pytha2.png)

정사각형 ABCD를 기준으로, 대각선이 c가 되는 직각 삼각형을 그린다.   

그러면 삼각형 ABE와 같은 모양이 된다.   
그리고, 각 모서리를 기준으로 돌려가면서 배치하면, 가운데 정사각형 EFGH를 남겨놓는 모양이 된다.

넓이를 비교하면,
- S1 = 전체 정사각형(ABCD)의 넓이 = $c \times c = c^2$
- S2 = 부분 도형들의 넓이의 함 = $\triangle ABE + \triangle BCF + \triangle GCD + \triangle AHD + \Box EFGH = 4 \times \frac{1}{2} \times a \times b + (b - a)^2$

S1 = S2 이므로,     
$c^2 = 2ab + b^2 - 2ab + a^2$   
$c^2 = a^2 + b^2$   
$a^2 + b^2 = c^2$

# 4. 삼각비

직각삼각형의 세 변의 길이 중 두 변의 길이간의 비례 관계를 나타내는 값이다.  
일반적으로 비례 관계는 분수로 나타낸다.     
또한 $\sin$과 $\cos$은 반비례한다.  

항상 빗변의 길이를 나눠야 될 물리량으로 생각하면 직관적으로 적용할 수 있다.     
밑변의 길이에서 나누면 코사인(cosine), 높이에서 나누면 사인(sine)이라고 한다.

![삼각비](/img/triratios0.webp)

엄밀하게는 직각삼각형에 대해 sine, cosine, tangent를 다음과 같이 정의한다.  
$$\sin A = \frac{a}{h}$$
$$\cos A = \frac{b}{h}$$
$$\tan A = \frac{a}{b}$$

그리고 이들을 역수로서 cosecant, secant, cotangent 함수를 다음과 같이 정의한다.
$$\csc A = \frac{1}{\sin A} = \frac{h}{a}$$
$$\sec A = \frac{1}{\cos A} = \frac{h}{b}$$
$$\cot A = \frac{1}{\tan A} = \frac{b}{a}$$

# 5. 삼각함수
삼각비에서 쓰이는 정의역을 예각($0^\circ$ 에서 $90^\circ$ 사이의 각)에서 일반각(기존의 예각은 물론 예각이 아닌 각까지 포함하는 더 넓은 개념)으로 확장시킨 것을 삼각함수라고 한다.

### 일반각과 삼각비
일반각을 정의하는 방법에는 도($^\circ$)를 단위로 하는 육십분법과 라디안(rad)을 단위로 하는 호도법이 있다.

- 육십분법(단위: $^\circ$)은 시초선을 기준($0^\circ$)으로 하여 1회전을 $360^\circ$로 정의하는 각이다.
- 호도법(단위: rad)은 부채꼴에서 중심각의 크기와 호의 길이가 반지름에 비례한다는 특징과, '원주가 지름의 $\pi$배(원주가 반지름의 $2\pi$배)'라는 성질을 이용하여 정의되는 각이다. (차원이 없다.)

### 좌표와 원으로 정의하기
![삼각함수](/img/trifunc0.svg)

좌표평면 상 원점 $O$가 중심인 단위원을 고려하자.    
단위원 위의 한 점 $P(x, y)$에 대해여 $x$축의 양의 방향을 시초선으로 잡는다.     
$O$를 중심으로 시초선에서 반시계 방향 회전을 각의 양의 방향으로 잡고, 그 각의 크기를 $\theta$라고 하면, 다음으로 정의한다.
$$\sin \theta := y$$
$$\cos \theta := x$$
$$\tan \theta := \frac{y}{x}\quad (x \neq 0)$$

동경이 몇 사분면에 위치하는지에 따라 삼각함수의 부호는 달라진다.

|동경의 위치|1사분면|2사분면|3사분면|4사분면|
|---|---|---|---|---|
|사인의 부호|$+$|$+$|$-$|$-$|
|코사인의 부호|$+$|$-$|$-$|$+$|
|탄젠트의 부호|$+$|$-$|$+$|$-$|

$\theta$가 예각일 때, 위의 관계식은 빗변의 길이가 1인 직각삼각형에서 삼각비를 정의했던 것과 완전히 같다.    
차이점은 (0 또는 음수가 될 수 없는)'길이' 개념에서 벗어나 '좌표'를 이용하기 때문에 직각삼각형에 구애받을 필요가 없고, 따라서 $\theta$가 일반각으로 확장된다.

다음과 같이 삼각함수의 역수를 정의한다.
$$\sec \theta := \frac{1}{\cos \theta} = \frac{1}{x} \quad (x \neq 0)$$
$$\csc \theta := \frac{1}{\sin \theta} = \frac{1}{y} \quad (y \neq 0)$$
$$\cot \theta := \frac{1}{\tan \theta} = \frac{x}{y} \quad (y \neq 0)$$

각각 '시컨트', '코시컨트', '코탄젠트'라 읽는다.     
또, 코시컨트는 $\cosec x$로 쓰기도 한다.

좌표평면 상 원점 $O$가 중심이고, 반지름이 $r$인 원 위의 점 $(x, y)$에 대해서도 동일한 방법으로 정의가 가능하며, 아래와 같다.
$$\sin \theta := \frac{y}{r}$$
$$\cos \theta := \frac{x}{r}$$
$$\tan \theta := \frac{y}{x}$$

주의해야 할 것은 거듭제곱 꼴로 나타낸 경우, 예를 들어 $\sin^n \theta$, 그것은 $n$번 함수를 합성한 것이 아닌 함숫값의 $n$제곱의 값을 의미한다.   
즉, $\sin^2 \theta = (\sin \theta)^2 \neq \sin(\sin \theta)$

# 6. 수와 집합
### 수 (Numbers):
수는 양, 음, 정수, 유리수, 실수 등으로 나타낼 수 있는 개념이다.     
여러 가지 형태와 특성을 갖는다.

1. 자연수 (Natural Numbers): 1, 2, 3, 4와 같이 양의 정수들을 의미한다.  
주로 자연적인 세기나 계산에 사용된다.
2. 정수 (Integers): 0, 양의 정수, 음의 정수를 포함한 수의 집합이다.     
양의 정수와 음의 정수는 무한대로 확정될 수 있다.
3. 유리수 (Rational Numbers): 두 정수의 나눗셈으로 나타낼 수 있는 수를 의미한다.    
이 때 분모는 0이 아니어야 한다.     
예를 들어 1/2, -3/4 등이 유리수이다.
4. 실수 (Real Numbers): 유리수와 더불어 모든 실수를 포함하는 집합이다.  
실수는 실제 세계의 대부분의 측정이나 계산에 사용된다.   
실수는 무한 소수로 나타낼 수도 있다.
5. 복소수 (Complex Numbers): 실수와 허수를 합한 수이다.     
허수는 실수와 곱하여 -1을 얻는 수로, i라는 기호로 표현한다.     
복소수는 a + bi 형태로 나타낼 수 있으며, 여기서 a는 실수 부분이고 bi는 허수 부분이다.

### 집합 (Sets):
집합은 원소들의 모임을 나타내는 개념이다.   
집합은 중복되지 않는 원소들로 구성된다.     
수학적으로 집합은 중괄호 {} 안에 원소를 나열하여 나타낼 수 있다.

예를 들어, A = {1, 2, 3}은 원소 1, 2, 3으로 구성된 집합 A를 나타낸다.   
또 다른 예로, B = {red, green, blue}는 색상을 나타내는 집합 B를 나타낸다.

집합의 특성:

- 원소 (Elements): 집합을 구성하는 각각의 개별 요소를 원소라고 한다.
- 원소의 중복: 집합은 중복된 원소를 허용하지 않는다.    
즉, 하나의 원소는 집합 내에서 유일하게 나타난다.
- 집합의 크기: 집합 내 원소의 개수를 집합의 크기 또는 원소의 개수라고 한다.
- 부분집합 (Subset): 집합 A의 모든 원소가 집합 B에도 속할 때, 집합 A는 집합 B의 부분집합이라고 한다.
- 합집합 (Union): 두 개 이상의 집합에서 모든 원소들을 모아 새로운 집합을 만들 때, 이를 합집합이라고 한다.
- 교집합 (Intersection): 두 개 이상의 집합에서 공통으로 포함된 원소들을 모아 새로운 집합을 만들 때, 이를 교집합이라고 한다.

집합 이론은 수학적 분석, 확률론, 그래프 이론 등 다양한 분야에서 활용되며, 수와 관련된 다양한 개념과 연산을 다루는데 사용된다.

# 6.1. 연산과 수의 구조
### 연산 (Operations):
연산은 수나 다른 개체들 사이에서 수행되는 계산 또는 작용을 의미한다.    
연산은 수학적으로 다양한 형태로 나타낼 수 있으며, 주요한 연산에는 다음과 같은 것들이 있다.

1. 덧셈 (Addition): 두 수를 더하는 연산이다.    
덧셈은 수의 합을 구하는 데 사용된다.
2. 뺄셈 (Substraction): 하나의 수에서 다른 수를 빼는 연산이다.  
뺄셈은 두 값 사이의 차이를 구하는 데 사용된다.
3. 곱셈 (Multiplication): 두 수를 곱하는 연산이다.  
곱셈은 수의 증가율, 면적 등을 계산하는 데 사용된다.
4. 나눗셈 (Division): 하나의 수를 다른 수로 나누는 연산이다.    
나눗셈은 비율, 분수 등을 표현하는 데 사용된다.
5. 지수 (Exponentiation): 수를 다른 수의 거듭제곱으로 나타내는 연산이다.    
a^n은 a를 n번 곱하는 것을 의미한다.
6. 제곱근 (Square Root): 어떤 수의 제곱이 특정한 값이 되도록 하는 수를 찾는 연산이다.

### 수의 구조:
수의 구조는 수들 간의 관계와 패턴을 이해하고 분석하는 데 도움을 준다.

1. 집합 구조: 수는 집합의 원소로 나타낼 수 있다.    
집합에는 원소 간의 연산인 합집합, 교집합 등의 연산이 있다.
2. 순서 구조: 수의 순서는 수열이나 수량을 나타내는 데 사용된다.     
수열은 수들이 순서대로 나열된 구조이다.
3. 대수 구조: 수의 대수 구조는 수들 간의 연산에 관한 구조를 의미한다.   
이에는 그룹, 반환, 체 등이 포함된다.
4. 유한성과 무한성: 수의 구조에는 유한한 수의 개수와 무한한 수의 개수가 있다.   
자연수 집합은 무한한 원소를 가지지만, 유한한 집합도 있을 수 있다.
5. 소수와 합성수: 소수는 1과 자기 자신만을 약수로 가지는 수이다.    
합성수는 두 개 이상의 양의 약수를 가지는 수이다.
6. 모듈로 구조: 모듈로 연산은 나눗셈의 나머지를 다루는 구조이다.    
이 구조는 순환 패턴이나 주기성을 분석하는 데 사용된다.
7. 순열과 조합: 순열은 원소들의 순서에 따른 나열을 의미하고, 조합은 원소들의 순서에 관계 없는 선택을 의미한다.  
이들은 주로 카운팅 문제나 확률 문제에서 사용된다.

수의 구조와 연산은 수학의 핵심 개념이며, 이를 통해 다양한 문제를 분석하고 해결할 수 있다.

# 6.2. 수의 표현
수는 다양한 방법으로 표현될 수 있다.    
각각의 표현 방법은 수의 특성이나 용도에 따라 선택될 수 있다.    

1. 십진법 (Decimal Notation):   
십진법은 일상 생활에서 가장 많이 사용되는 표현 방법이다.    
숫자 0부터 9까지의 10개의 기호를 사용하여 수를 나타낸다.    
수의 위치가 변화함에 따라 그 값이 달라지는 위치 표기법을 사용한다.      
예를 들어, 365는 3 * 10^2 + 6 * 10^1 + 5 * 10^0으로 표현된다.

2. 이진법 (Binary Notation):    
이진법은 0과 1의 두 개의 기호만을 사용하여 수를 나타내는 방법이다.      
컴퓨터 시스템에서 주로 사용되며, 전기 신호의 온/오프 상태로 표현된다.   
예를 들어, 101은 1 * 2^2 + 0 * 2^1 + 1 * 2^0으로 표현된다.

3. 프로그래밍에서의 표현:   
프로그래밍 언어에서는 정수, 부동소수점, 복소수 등 다양한 형식으로 수를 표현할 수 있다.      

4. 지수 표기법 (Scientific Notation):   
매우 크거나 작은 수를 간결하게 표현하기 위해 지수 표기법을 사용한다.    
예를 들어, 3,000,000은 3 * 10^6으로 표현할 수 있다.

5. 분수 (Fractions):    
분수는 두 개의 정수를 나누어 나타내는 표현 방법이다.    
분자와 분모로 구성되며, 분자는 분모를 나눈 몫을 나타낸다.   
예를 들어, 1/2는 분자가 1이고 분모가 2인 분수를 나타낸다.

6. 소수 (Decimal Fractions):    
소수는 십진법에서 소수점을 가진 수로, 정수와 소수 부분으로 나누어 나타낸다.     
예를 들어, 3.14159sms 정수 부분이 3이고 소수 부분이 0.14159인 소수이다.

7. 혼합수 (Mixed Numbers):  
정수 부분과 분수 부분을 함께 가진 표현 방법이다.    
예를 들어, 2 1/2는 정수 부분이 2이고 분수 부분이 1/2인 혼합수를 나타낸다.

8. 복소수 (Complex Numbers):    
실수와 허수 부분으로 구성된 수이다.     
a + bi 형태로 나타내며, a는 실수 부분이고 bi는 허수 부분이다.

이러한 다양한 표현 방법은 수학적 계산, 과학, 엔지니어링, 프로그래밍 등 다양한 분야에서 사용되며, 특정한 문제나 상황에 맞게 선택하여 사용한다.

# 7. 함수
함수는 수학과 다양한 분야에서 중요한 개념으로 사용되는 개념이다.    
함수는 입력값을 받아서 특정한 규칙에 따라 출력값을 계산하는 규칙이나 연산을 나타내는 수학적 객체이다.   
함수는 다양한 형태와 목적으로 사용된다.

### 함수의 구성요소:
1. 입력 (Domain): 함수에 입력되는 값들의 집합을 의미한다.   
이 집합은 함수가 정의되는 범위를 결정한다.
2. 출력 (Codomain 또는 Range): 함수가 입력값을 대응시켜 계산한 결과값들의 집합이다.     
함수의 출력값은 입력값에 따라 달라질 수 있다.
3. 규칙 (Rule): 함수가 입력값을 어떤 연산에 따라 출력값으로 변환하는지를 나타내는 부분이다.     
이 규칙은 함수의 정의에 따라 달라진다.

### 함수의 표기법:
함수는 보통 다음과 같이 표기된다: f(x), g(y), h(z)와 같이 함수 이름 다음에 입력값을 나타내는 변수를 괄호 안에 표기한다.     
함수 이름은 임의로 지정할 수 있으며, 입력 변수도 함수에 따라 다를 수 있다.

### 예시:
1. 선형 함수 (Linear Function): 가장 간단한 함수 중 하나로, 출력값이 입력값에 대해 일정한 비율로 변하는 함수이다.   
예를 들어, f(x) = 2x는 입력값을 2배씩 증가시켜 출력값을 계산한다.
2. 제곱 함수 (Quadratic Function): 출력값이 입력값의 제곱에 관련된 함수이다.    
예를 들어, g(x) = x^2는 입력값을 제곱하여 출력값을 계산한다.
3. 삼각 함수 (Trigonometric Function): 삼각형의 각도와 변의 비율에 관련된 함수로, 삼각함수(sin, cos, tan 등)는 각도에 따른 값을 계산한다.
4. 지수 함수 (Exponential Function): 출력값이 입력값의 지수에 관련된 함수로, f(x) = e^x는 입력값의 지수에 해당하는 값들을 출력값으로 계산한다.

### 함수의 활용:
함수는 수학뿐만 아니라 과학, 공학, 경제학, 컴퓨터 과학 등 다양한 분야에서 활용된다.     
함수는 데이터 분석, 모델링, 문제 해결 등에 사용되며, 복잡한 현상을 간단한 규칙으로 설명할 수 있는 도구로 활용된다.      
함수의 연속성, 미분, 적분 등의 특성은 미적분학과 같은 수학 분야에서 중요한 개념이다.

# 7.1. 함수의 개념과 종류
### 함수의 개념:
함수는 입력과 출력 간의 대응 관계를 정의하는 수학적 규칙이다.   
어떤 집합의 각 원소(입력)가 다른 집합의 원소(출력)와 대응된다.      
이때, 하나의 입력에 대해 하나의 출력이 대응되어야 한다.     
함수는 특정한 규칙에 따라 입력값을 처리하고 연산하여 출력값을 생성하는 과정을 나타낸다.

수학적으로 함수는 다음과 같이 표기된다:     
$f : X \rightarrow Y$   
여기서 $f$는 함수의 이름, $X$는 입력의 집합(도메인), $Y$는 출력의 집합(치역)을 나타낸다.    
입력 $x$가 주여졌을 때, 함수 $f(x)$로 나타내며 이는 입력 $x$에 대응되는 출력값을 의미한다.

### 함수의 종류:
1. 선형 함수 (Linear Functions): 출력이 입력에 대해 일정한 비율로 변화하는 함수이다.    
$f(x) = ax + b$ 형태로 나타낼 수 있으며, $a$는 기울기를, $b$는 y 절편을 나타낸다.
2. 다항 함수 (Polynomial Functions): 여러 항의 합으로 표현되는 함수로, $f(x) = a_nx^n + a_{n-1}x^{n-1} + ... + a_1x + a_0$ 형태이다.    
n은 차수를 나타내며, $a_n$부터 $a_0$은 계수이다.
3. 지수 함수 (Exponential Functions): 출력이 입력값의 지수에 관련된 함수이다.   
$f(x) = a^x$ 형태로 나타낼 수 있으며, $a$는 기저이며 양수여야 한다.
4. 로그 함수 (Logarithmic Functions): 입력값의 로그에 관련된 함수이다.      
$f(x) = \log _a(x)$ 형태로 나타낼 수 있으며, $a$는 양수인 상수이며, 입력 $x$는 양수여야 한다.
5. 삼각 함수 (Trigonometric Functions): 삼각형의 각도와 변의 비율에 관련된 함수로, 삼각함수인 $\sin (x), \cos (x), \tan (x)$ 등이 있다.
6. 복소 함수 (Complex Functions): 복소수를 입력값이나 출력값으로 가지는 함수이다.   
$f(z)$ 형태로 표기되며, $z$는 복소수이다.
7. 계단 함수 (Step Functions): 입력값의 범위에 따라 출력값이 불연속적으로 변화하는 함수이다.    
주로 디지털 신호 처리 등에 활용된다.
8. 비선형 함수 (Nonlinear Functions): 선형이 아닌 형태로 출력값이 입력값에 대해 변화하는 함수들을 포함한다.     
다항 함수, 지수 함수, 로그 함수 등이 비선형 함수에 해당된다.