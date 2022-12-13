# baekJoon
baekJoon vsCode Cpp solution

# helped
- Algorithmic   
　  
- MatheMatical  
  　
- Linguistic  
1008, 4344 - `cout.precision(streamsize)`, `cout << fixed`, `setprecisioin(streamsize)`  
https://url.kr/n2grjf  
10809 - `fill_n`  
https://url.kr/b6jk1r  
15552 - `ios::sync_with_stdio(false);`, `cin.tie(NULL);`, `cout.tie(NULL);`, ```endl VS '\n'```  
https://url.kr/dv271f  
15596 - `vector<T>` & `#include <vector>`    
https://blog.naver.com/president304/222422474064  


# Special(onMyWay || Hard)
2675 - Mine is O(n^2) not O(n^3) : M

　  
   　  
      　  
         　  
            　  
               　  　  
                     
## 1. 출력 숫자의 자릿수 고정
`cout.precision(), cout.precision(streamsize)`

## 2. C++ 입출력 속도 단축  

### 방법 1.
```c++
ios::sync_with_stdio(false);
cin.tie(NULL);
cout.tie(NULL);
```
이 코드는 입출력의 속도를 단축시킨다  

#1 `ios::sync_with_stdio(false);` 
찾아본 바로는 c++에서는 c의 입출력 방식을 추가??로 이용한다고 한다  
그렇기에 c++과 c의 입출력이 같이 일어나지 않도록 동기화를 끊어 c++만의 입출력 속도를 증진한다고 한다  
(c++과 c의 버퍼가 같이 이용되는 것이 아닌 c++의 버퍼만 이용하게된다)

다만 이 코드를 이용하려면 단일스레드 환경이어야 하며, c 방식의 입출력(printf(), getchar())를 사용할 수 없다고 한다  

#2 `cin.tie(NULL);`, `cout.tie(NULL);`  
참고자료를 읽어볼 것(정확히 정리가 안됨)  

### 방법 2.
```
#include <cstdio>

...

  scanf("%d", &num);
  printf("%d\n");
```

### 입출력 속도 
C11 scanf() - 0.92s  
C++17 cin - 2.17s  
C++17	ios_base::sync_with_stdio(false); cin.tie(NULL);	0.5938s  
C++17	ios_base::sync_with_stdio(false);	0.6348s  
  
C11 printf - 0.91s  
C++17 printf(c++) - 0.86s  
C++17	ios_base::sync_with_stdio(false); cout << i << '\n'; - 0.827s  
C++17	ios_base::sync_with_stdio(false); cout.tie(NULL); cout << i << '\n'; - 0.8272s  
(cout.tie(NULL)이 사용하지 않으면 0.0002s정도 빨라진다고 하는데.. 막상 코드에서 제외해보니 그렇지 않았다)  
<img width="306" alt="스크린샷 2022-01-31 오후 7 34 50" src="https://user-images.githubusercontent.com/58582985/151778602-ad510856-0a49-4bbe-bc42-aa7df1cd4f9f.png">


+ 참고자료 - https://jaimemin.tistory.com/1521  
+ 참고자료 - https://leeeegun.tistory.com/4  
+ 참고자료 - https://www.acmicpc.net/blog/view/56 (입력속도)  
+ 참고자료 - https://www.acmicpc.net/blog/view/57 (출력속도)  

## 3. 리스트 한 번에 채우기
```c++
int arr[100];

fill_n(arr, 100, 0);        //fill_n(배열의 이름, 길이, 채우는 값)
```
