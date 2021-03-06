---

title: "[뇌를 자극하는 알고리즘] ch09 그래프 section3 그래프 순회"
date: 2020-05-15
categories: ['algorithm']
tags: ['algorithm', '뇌를 자극하는 알고리즘', '한빛미디어']

---

# 9장 그래프

## section 3. 그래프 순회: 그래프를 따라 산책하기

### 그래프 순회
* 트리/그래프와 같은 비선형 구조의 자료 탐색에서 어떠한 데이터나 상황에 연결된 여러 가지 경우를 모두 탐색하기 위해 효과적으로 사용
1. 너비 우선 탐색
2. 깊이 우선 탐색

### 깊이 우선 탐색(Depth First Search; DFS)
- 동작 방식
  > 1. 시작 정점을 밟은 후 이 정점을 '방문했음'으로 표시
  > 2. 이웃하고 있는 정점, 즉, 인접 정점 중에 아직 방문하지 않은 곳을 선택하고 이를 다시 시작정점으로 삼아 다시 깊이 우선 탐색을 시작(1단계를 다시 수행 -> 재귀함수)
  > 3. 정점에 더 이상 방문하지 않은 인접 정점이 없으면 이전 정점으로 돌아가서 2단계를 다시 수행
  > 4. 이전 정점으로 돌아가도 더 이상 방문할 이웃이 없다면 모든 정점을 방문했다는 뜻으로 탐색 종료
  
### 너비 우선 탐색(Breadth First Search; BFS)
- 동작 방식
  > 1. 시작 정점을 '방문했음'으로 표시하고 큐에 삽입
  > 2. 큐로부터 정점을 제거. 제거한 정점에 이웃에 인접 정점 중 아직 방문하지 않은 정점을 '방문했음'으로 표시하고 큐에 삽입
  > 3. 큐가 빌 때까지 이 과정을 반복. 큐가 비면 탐색 종료
