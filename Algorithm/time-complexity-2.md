# **Time complexity** (시간 복잡도)

 **이진탐색** 시간복잡도 구하기 
 
```java 
int findPosition(int[]sortedInputs,int target){
  ...
}
```

# Worst case : 찾는게 없을 때...

매번 실행할 떄 마다 1/2씩 사이즈가 줄어든다.. 몇 번만에 사이즈는 1이 되는가?

input size 를 N 이라고 했을 때 

    N*(1/2)ᵏ =1 (k를 구하는 게 핵심)
    
    N/2ᵏ =1 -> N = 2ᵏ -> log₂N = log₂2ᵏ -> k 
  
    k = log₂N
    
점근적 표시법으로 표현하면 
    
    θ(logN)
    


# Best case : 한 번에 찾았을 때...
  
    θ(1)

    
    
    O(logN) (upper bound)


<img width="1189" alt="image" src="https://user-images.githubusercontent.com/76646494/184900277-af36e49d-a144-48b5-bea3-ef998f25bfc9.png">



# 예제 1
```java 
void prints(int[] inputs){
for (int i = 0; i < inputs.length; i++){
  for(int j = 0; j < inputs.length; j++){
    System.out.println("최고십니다");
    }
  }
}
```

이중 루프이므로 N * N = N²

점근적 표기법으로는 

    θ(N²)


# 예제 2 

```java 
void prints(int[]inputsA, int[]inputsB){
for (int i = 0; i < inputsA.length; i++){
  System.out.println("최고");
}

for(int i = 0; i < inputsB.length; i++){
  System.out.println("굿굿");
   
  }
}
```

루프가 동등한 위치에서 도는 유형이다.

   θ(max(N,M)) -> θ(N+M)

input 사이즈 N 또는 M 중 더 큰 사이즈가 영향을 미치기 때문에  표현한다.


# 예제 3
```java 
void prints(int[]inputsA, int[]inputsB){
for (int i = 0; i < inputsA.length; i++){
  for(int j = 0; j < inputsB.length; j++){
    System.out.println("곱한다.");
    }
  }
}
```

  θ(N*M)  
  
  #시간 복잡도 속도 비교
  
 **O(1) < O(logN) < O(N) < O(N*logN) < O(N²) < O(2ⁿ) < O(N!)**


 ----> 오른쪽으로 갈 수록 성능이 안좋아진다.



# 왜 Big-O 표기법을 많이 쓸까?

빅오 표기법으로도 다 표현 할 수 있어서...
키보드에 세타와 오메가가 없어서 



**출처** [쉬운코드](https://www.youtube.com/watch?v=tTFoClBZutw)
