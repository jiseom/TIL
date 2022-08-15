# **Time complexity** (시간 복잡도)

```java
int[] multiply(int[]inputs,int multiplier){
int[] nums = new int[inputs.length];
for(int i = 0; i < inputs.length; i++){
      nums[i] = inputs[i] * multiplier 
  }
 return nums;
}
```
위의 함수가 존재할 때 함수의 실행 시간을 가령 초(sec)로 표현하려면, 하드웨어의 성능에 따라 실행 시간이 차이가 나므로 표현하기 어렵다.

그래서 **실행 시간** (running time)을 함수/알고리즘 수행에 필요한 스텝(step) 수로 표현할 수 있다.

위 함수의 각 라인을 수행하기 위해 필요한 스텝 수는 상수(constant)라고 했을 때,

|                |cost               |times                        |
|----------------|-------------------------------|-----------------------------|
|int[] nums = new int[inputs.length];|c1         |1    |
| for(int i = 0; i < inputs.length; i++){    |c2          |N+1         |
|nums[i] = inputs[i] * multiplier      |c3|N|
|return nums;      |c4|1|

각 라인마다 cost * times 해서 더해줘야 한다.

T(N) = c1* 1 + c2*(N+1) + c3*N + c4

= (c2 + c3)*N + c1 + c2 + c4

= a*N + b 

input 사이즈 = N 이 작을 때는 실행 시간을 계산하는 것이 의미가 없다.

     
N 이 커질수록 최고차항만 의미가 있고 input 사이즈 N에 대한 최고차항의 계수도 의미가 없기 때문에 (a 생략) 이렇게 표현할 수 있다.
     
       θ(N) 
   

# 점근적 분석
     
임의의 함수 N이 무한대로 갈 때 어떤 함수 형태에 근접해지는지 분석하는 것으로 

앞서 나온  **θ(N)** 은 점근적 표기법이라고 한다.


#시간 복잡도
함수의 실행 시간을 표현하는 것으로 주로 점근적 분석을 통해 실행 시간을 단순하게 표현하며 이 떄 점근적 표기법으로 표현한다.

     
```java
boolean exists(int[]inputs,int target){
  for(int i = 0; i<inputs.length; i++){
    if(inputs[i] == target){
      return true;
      }
    }
  return false;
}

```
위 함수의 시간 복잡도를 구해보려면 함수의 파라미터 데이터에 따라 실행 시간이 조금씩 다르다.

찾으려는 target이 앞에 있으면 best case 인데 target이 마지막에 있거나 배열 안에 없을 경우 worst 케이스라고 할 수 있다.

**lower bound (하한선)** : 함수 실행 시간은 아무리 빨라도 아무리 빨라도 상수 시간 이상이다. (best case)

    Ω(1)

**upper bound (상한선)** : 함수 실행 시간은 아무리 오래 걸려도 N에 비례하는 정도 이하이다.  (worst case)
    
    O(N)
    
    


![image](https://user-images.githubusercontent.com/76646494/184673968-3ca91fb6-7e67-4907-9c44-dad5f328be04.png)


![image](https://user-images.githubusercontent.com/76646494/184674186-d454fbf4-120b-4923-871b-67962b962303.png)





**출처** [쉬운코드](https://www.youtube.com/watch?v=tTFoClBZutw)
