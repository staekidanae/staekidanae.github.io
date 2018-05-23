---
layout: post
title:  "정렬 알고리즘을 배우며 알게된것?"
date:   2018-05-23
categories: [blog, jekyll]
---

병원에 다녀오느라 앞부분을 전혀 못들었다. 일단 앉아서 화면을 보니 순차검색이란 중요한부분을 실습중이었다...???
어제자 수업이 분명 제너레이터까지 하고 끝났는데 2시간동안 어떤일이 있었는진 모르겠지만 순차검색 실습중이었다.

어떤식으로 만들어야하는지 지침이 안보여서 일단 한번 도전해보았다.
def sequiential_search(string, key):
    a = 0
    while 1 > 0:
        try:
            if string[a] == key:
                return a
                break
            else:
                a += 1
        except:
            return -1

이렇게 만들었는데 역시나 선생님이 만드신 코드는 훨씬 간단명료했다...ㅠㅠ
선생님 코드를 보면 나는 왜이렇게 짰을까 간단하게 생각하지 라는 자책을 한다
슬프다
아 그리고 몰랐던 사실인데 반복문에서 return이 나오면 그냥 반복문이 끝나는거였나보다... 위에서도 return a 한 뒤 break 까지 넣어썼는데 쓸데없는 짓이었다.

그리고 대망의 선택정렬
열심히 삽질했다.
최소값나오는건 무난하게 했는데 자리 배치하는거에서 막혔다
append로 첫인덱스 새로넣고 remove로 지우고 index[0]에 미니멈값넣고하는식으로
하다가 복잡해져서 잘하던것까지 망쳤다.

새로운 맘으로 선생님의 코드를 보다보니 시원하게 정리가 잘 되었다

혼자 새롭게 다시 짜보려고 하다보니

listt = [9,1,6,-5,8,4,3,2,0,-3]

range_list = len(listt)

for x in range(range_list):
    min_index = x
    print(listt)
##    for y in range(range_list): ##
        if listt[min_index] > listt[y]:
            min_index = y
        
    if min_index != x:
        listt[x], listt[min_index] = listt[min_index], listt[x]
print(listt)
## ## 부분에서 실수가 있던걸 깨달았다
두번째 반복문에서 그냥 단순 범위로 지정해놓으면
다시 루프돌때 첫 범위 그대로 되어버리니
계속 미니멈값이 오른쪽으로 한칸씩 이동하던거였다..ㅋㅋ(첫번째 루프에서 미니멈값이 인덱스 0번으로 갔으니깐)

그래서 첫 루프의 변수 x를 다시금 범위에 넣어주니 해결되었다.

알고리즘은 중요한거같다. 이런걸 구현할 줄 알아야 프로그램을 짤때 구상력이 좋아질 것 같다.
파이썬 공부하는주는 알고리즘을 같이 공부하는 목표를 세웠다. 책도있으니
그대로 구현하는걸 해봐야지.

화이팅하자

