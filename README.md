# Artificial-intelligence_Theory

# 제약조건 만족 문제
__백트랙킹 탐색(깊이우선)__ : 허용되는 것 대입. 허용 안되는 것 이전단계로 돌아가서 다시.  
__제약조건 전파__ : 인접 변수, 허용되지 못하는 값 제거. =>해당 레벨에서 선택 가능한 모든 경우를 한 판에 동시에 나열(해당 열 중복 가능), 그 다음 단계에서는 이전 단계에서 하나를 선택 후 반복  
백트랙킹 탐색과 제약조건 전파의 차이 : 백트랙킹은 일 대 일 대응만, 제약조건 전파는 일 대 다  

# 추론
__귀납__ : 복수의 사실 일반화 : 일반적인 패턴
__연역__ : 참인 사실(명제) → 새로운 참인 사실(명제)

# 의미망
__is-a__ : A == B 이다 예) is-a(조류,동물) 조류→동물  
__has-a__ : 부분, 조각 예) has-a(조류,깃털) 조류→깃털  

# 불확실성  
__확신도__ : 약한 관련성 [-1,1]  
__퍼지이론__ : 부정확한 언어  

# 규칙에 대한 추론 결과의 확신도  
1.__AND__  
`
문제) p1(cf_1) = 0.5, p2(cf_2) = 0.9, p3(cf_3) = 0.7, R(cf_r)=0.5
`

IF p1(cf_1)AND p2(cf_2)AND p3(cf_3)THEN R(cf_r):min(cf_1,cf_2,cf_3)*cf_r  
   0.5         0.9         0.7          0.5    =   0.5      *     0.5  

__풀이__  
```
cf(R)=min{(cf_1), (cf_2), (cf_3)} *cf( p1 AND p2 AND p3 → R)  
cf(R)=cf(p1) * cf(p1 AND p2 AND p3 → R)  
cf(R)=0.5*0.5 = 0.25  
```

2.__OR__  
`
IF p1(cf_1) OR p2(cf_2) OR p3(cf_3) THEN R(cf_r):max(cf_1,cf_2, cf_3)*cf_r
   0.5         0.9         0.7           0.5    =    0.9       *      0.5
`
__풀이__
```
cf(R)=max{(cf_1), (cf_2), (cf_3)} *cf( p1 OR p2 OR p3 → R)
cf(R)=cf(p2) * cf(p1 OR p2 OR p3 → R)
cf(R)=0.9*0.5 = 0.45
```
# 퍼지 집합[0,1]  
집합론 ↔ 퍼지 집합__(이분적 X)__  
__정성적 표현(성분,성질_큰,비싼..)을 정량적(0에서 1사이의 값으로) 표현화 시켜야 함__  
소속 정도(부분적 참)  

# 퍼지추론  
그래프 __높이__
and : 최소값
or : 최대값

# 알파-베타 가지치기 설명영상 입니다.  
[alpha-beta-prunning](https://drive.google.com/file/d/1rjcbqTk0BlidDBo3k9DL6aOjXeNAEOTU/view?usp=sharing, "알파-베타 가지치기 구글 드라이브 설명영상 입니다" )
