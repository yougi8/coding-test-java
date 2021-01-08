## 이것이 취업을 위한 코딩테스트다  
[ 나동빈 저 ] " 이것이 취업을 위한 코딩테스트다 with 파이썬 "  자바 코드 저장  

***  

### Part2  
#### Chapter 3. 그리디  

    * 현재 상황에서 지금 당장 좋은 것만 선택하는 알고리즘  
    * 기준에 따라 좋은 것을 선택하는 문제  
     -> 문제에서 '가장 큰 순서대로', '가장 작은 순서대로' 라는 기준을 말해줄 때가 많다.  
    
* 거스름돈 문제 : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch3/ch3_1.java)   

      * 그리디 문제로 풀 수 있는 이유  
        - 가장 큰 단위가 항상 작은 단위의 배수이기 때문.   
          - 예를 들어, 동전이 500원과 400원이라면 둘은 배수 관계가 아니기 때문에 그리디를 적용할 수 없다.  
          - 500원은, 100원, 50원, 10원의 배수 관계이기 때문에 그리디가 최선의 방법이 될 수 있다.  
          
      * 방법 : '가장 큰 화폐 단위부터' 돈을 거슬러 주는 것   
      
* **동빈이의 큰 수의 법칙** : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch3/ch3_2.java)  

      * 방법 : 반복되는 수열에 대해서 파악해야 한다.  
      
* **숫자 카드게임** : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch3/ch3_3.java)  
     
      * 방법 : 각 행마다 가장 작은 수를 찾은 뒤에 그 수 중에서 가장 큰 수를 찾기  
      
      
* **1이 될 때까지** : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch3/ch3_4.java)  

      * 방법 : 최대한 많이 나누기  
        -> 나누는 것이 1을 빼는 것보다 숫자를 훨씬 많이 줄일 수 있기 때문

#### Chapter 4. 구현  

    * 구현 : 머릿속에 있는 알고리즘을 소스코드로 바꾸는 과정  
    * 구현 문제 : 풀이를 떠올리는 것은 쉽지만 소스코드로 옮기기 어려운 문제  

* 상하좌우 :  [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch4/ch4_1.java)  

      * 시뮬레이션 유형으로 분류됨  
      * 문자열 한 줄을 가져오기 위해서 버퍼 비우기 필수 !!  
        -> nextLine()은 남은 것을 다 문자열로 가져오기 때문에, 
           앞서 nextInt()로 값을 받고 엔터를 치는 순간 빈 공간을 입력받은 것이 되기 때문이다.  
        -> keyboard.nextLine();  
      * 방법 : 상하좌우를 switch-case문을 통해 저장해놓고, 적용해보기   
        
* 시각 :  [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch4/ch4_2.java)  

      * 모든 경우는 86,400가지이다.   
      * 계산이 금방 되기 때문에, 모든 경우를 하나씩 세서 풀 수 있다.  
      * 완전 탐색(Brute Forcing) 문제 유형이라고 한다.  
      * 방법 : 00시 00분 00초 부터 N시 59분 59초까지 모든 경우를 돌면서 3이 있는지 체크  
      
* **왕실의 나이트** :  [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch4/ch4_3.java)  

      * 2차원 배열이 등장하는 전형적인 구현 문제  
      * 방법 : 나이트가 움직일 수 있는 방향들은 2차원 배열에 저장해놓고, 주어진 위치에서 하나씩 움직여보는 것.  
        -> 움직였을 때 판을 벗어나지 않으면 count+1  
      
      
* **게임 개발** :  [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch4/ch4_4.java)  

      * 전형적인 시뮬레이션 문제
      * 삼성전자 공채 코딩 테스트에서 자주 출제되는 대표적인 유형
      * dx,dy와 같이 별도의 방향 리스트를 만드는 것이 효과적이다.

#### Chapter 5. DFS / BFS `그래프 탐색 알고리즘`  
  ```  
  # 스택 자료구조  
   -> 선입후출 ( 입구와 출구가 동일한 형태 ex.프링글스 과자 통 )  
   -> 자바에서  
       - Stack<Integer> s = new Stack<>();  
       - 삽입 : push  
       - 삭제 : pop  
  ```       
  ```       
  # 큐 자료구조  
   -> 선입선출 ( 입구와 출구가 모두 뚫려있는 형태 ex.터널, 대기표 )  
   -> 자바에서 
       - Queue<Integer> s = new LinkedList<>();  
       - 삽입 : offer  
       - 추출(삭제)&출력 : poll  
  ```       
  ```      
  # 재귀 함수(Recursive Function)  
   -> 자기 자신을 호출하는 함수  
   -> 재귀 함수의 종료 조건을 반드시 명시해야 한다.  
   -> 예 : 팩토리얼 문제, 유클리드 호제법(최대공약수 계산) 문제  
  ```   
  ```   
  # DFS ( 깊이 우선 탐색 )  
   -> 깊은 부분을 우선적으로 탐색하는 알고리즘  
   -> 스택 자료구조(or 재귀함수)를 이용 
     1. 탐색 시작 노드를 스택에 삽입하고 방문 처리를 한다.  
     2. 스택의 최상단 노드(제일 최근에 들어온 노드)에 방문하지 않은 인접 노드가 하나라도 있으면, 
        그 노드를 스택에 넣고 방문 처리를 한다.  
        방문하지 않은 인접노드가 없으면 스택에서 최상단 노드를 꺼낸다(스택에서 삭제).  
     3. 더 이상 2번의 과정을 수행할 수 없을 때까지 반복한다.   
  ```  
  ``` 
  # BFS ( 너비 우선 탐색 )  
   -> 가까운 노드부터 탐색하는 알고리즘  
   -> 큐 자료구조 이용  
     1. 탐색 시작 노드를 큐에 삽입하고 방문 처리를 한다.  
     2. 큐에서 노드를 꺼낸 뒤에 해당 노드의 인접 노드 중에서 방문하지 않은 노드를 
        모두 큐에 삽입하고 방문 처리를 한다.  
     3. 더 이상 2번의 과정을 수행할 수 없을 때까지 반복한다.  
  ```  

 * DFS 기본 구현 : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch5/ch5_1.java)  
 
 * BFS 기본 구현 : [Java 코드](https://github.com/yougi8/coding-test/blob/master/ch5/ch5_2.java)  
 
 * **음료수 얼려 먹기** :    
 
 * **미로탈출** :  
 
 ### chapter 6. 정렬  
  정렬 : 데이터를 특정한 기준에 따라 순서대로 나열하는 것  
  
   #### 선택 정렬  
   
         -> 처리되지 않은 데이터 중에서 '가장 작은 데이터'를 선택해 맨 앞과 바꾸는 것을 반복    
         -> ex. 7 5 9 0 3  
                0 | 5 9 7 3  
                0 3 | 9 7 5  
                0 3 5 | 7 9  
                정렬 끝  
          -> 이중 반복문을 활용하여 처리 
          -> 시간 복잡도 : O(N^2)  
             -> 가장 작은 수를 찾아서 N번만큼 맨 앞으로 보내야 함  
             -> N + (N - 1) + (N - 2 ) + ... + 2  
          
   #### 삽입 정렬  
      
          -> 처리되지 않은 데이터를 하나씩 골라 적절한 위치에 삽입  
          -> ex. 7 5 9 0 3  (7은 정렬이 되었다고 가정. 5부터 위치 판단 시작)  
                 5 7 9 0 3  (5가 7의 왼쪽으로)  
                 5 7 9 0 3  (9가 7의 오른쪽으로)  
                 0 5 7 9 3  (0이 5의 왼쪽으로)  
                 0 3 5 7 9  (3이 0의 오른쪽으로)  
          -> 이중 반복문 활용하여 처리  
          -> 시간 복잡도 : O(N^2)  
          -> 현재 리스트의 데이터가 거의 정렬되어 있는 상태라면 매우 빠르게 동작 (최선 : O(N))
          
   #### 퀵 정렬  
    
          -> 기준 데이터를 설정하고, 그 기준보다 큰 데이터와 작은 데이터의 위치를 바꾸는 방법  
          -> 기본 : 첫 번째 데이터를 기준 데이터(Pivot)로 설정  
             -> 왼쪽에서부터 pivot보다 큰 값, 오른쪽부터 pivot보다 작은 값을 고른다.  
             -> 이때 큰 값과 작은 값이 교차되는 순간, 작은 값과 pivot을 바꾼다.  
             -> 바꾼 후 pivot 위치는 고정이 된다.  
          -> ex. 7 5 9 0 3 (pivot : 7)  
                 7 5 3 0 9 (pivot : 7)  
                 0 5 3 | 7 | 9 (교차 -> 7 고정, 새로운 pivot : 0)  
                 0 | 3 5 | 7 | 9 (교차 -> 0 고정, 새로운 pivot : 3)    
                 0 | 3 | 5 | 7 | 9 (교차 -> 3 고정 )  
          -> 시간 복잡도   
            -> 평균 : O(NlogN)  
            -> 최악 : O(N^2)  
            
   #### 계수 정렬  
   
         -> 데이터의 크기 범위가 정수 형태로 표현 될 수 있을 때만 사용 가능  
         -> 매우 빠르게 동작함  
           -> 개수를 count하는 리스트를 따로 만든다.
           -> 정렬 할 리스트에서 왼쪽부터 해당하는 값의 count list의 값을 1씩 증가시킨다.  
           -> 그 후 count list의 인덱스 0에 해당하는 값부터 해당 값만큼 인덱스 번호를 출력한다.  
         -> 동일한 값을 가지는 데이터가 여러 개 등장할 때 효과적 ( 성적을 나열할 때 )  
         -> 시간 복잡도 : O(N + K)  
   
   정렬 알고리즘 | 시간 복잡도 | 공간 복잡도 | 특징  
   ---| :--: | ---:  
   `선택 정렬` | O(N^2) | O(N) | 아이디어가 매우 간단합니다.  
   `삽입 정렬` | O(N^2) | O(N) | 데이터가 거으 ㅣ정렬되어 있을 때는 가장 빠릅니다.  
   `퀵 정렬` | O(NlogN) | O(N) | 대부분의 경우에 가장 적합하며, 충분히 빠릅니다.  
   `계수 정렬` | O(N + K) | O(N + K) | 데이터의 크기가 한정되어 있는 경우에만 사용이 가능하지만 매우 빠르게 동작합니다.  
            
            
            
          
          
          
