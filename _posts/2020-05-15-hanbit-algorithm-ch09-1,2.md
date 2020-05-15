---

title: "[뇌를 자극하는 알고리즘] ch09 그래프 section 1 & 2"
date: 2020-05-15
categories: ['algorithm']
tags: ['algorithm', '뇌를 자극하는 알고리즘', '한빛미디어', '그래프', 'graph']

---

# 9장 그래프

## section 1. 그래프를 소개합니다
* 그래프의 정의
  - 그래프는 '정점의 모음'과 이 정점을 잇는 '간선의 모음'과의 집합
  - 정점의 집합을 V, 간선을 집합을 E, 그리고 그래프를 G라고 했을 떄 G = (V, E) 이다

* 용어
  - 정점(vertex): 
  - 간선(edge):
  - 인점(adjacent): 간선으로 연결된 두 정점, 이웃 관계
  - 경로(path): 간선을 통해 이웃이 된 정점이 형성하는 관계
  - 사이클(cycle): 어느 경로가 정점 하나를 두 번 이상 거치는 경로
  - 연결성(connectivity): 무방향성 그래프 내의 두 정점 사이에 경로가 존재한 경우

## section 2. 그래프의 표현
* 정점: 어떤 자료구조로도 쉽게 표현 가능
* 결국 그래프의 표현은 간선의 표현 문제로 귀결
  - 인접 행렬(adjacency matrix)
  - 인접 리스트(adjacency list)
  
|     | 장점 | 단점 |
| --- | --- | --- |
| 인접 행렬 | 인접 여부를 빠르게 파악  | 메모리소비가 큼  |
| 인접 리스트 | 메모리 소비가 적음 <br>정점, 간선의 삽입이 빠름  | 인접 여부를 파악하기 위해 순차 탐색이 필요 |


## 구현 소스
~~~
class Vertex:
    def __init__(self, data):
        self.data = data
        self.visited = False
        self.adjacent_list = list()
~~~
~~~
class Edge:
    def __init__(self, weight=0, v_from=None, v_to=None):
        self.weight = weight
        self.v_from = v_from
        self.v_to = v_to
~~~
~~~
class Graph:
    def __init__(self):
        self.vertex = []
    def show_graph(self):
        print("***** Print graph *****")
        for idx, item in enumerate(self.vertex):
            print(idx, ":", end='')
            for item in item.adjacent_list:
                print("%d[%d]" %(item.v_to, item.weight), end='')
            print()
    def del_graph(self):
        for i in self.vertex:
            i.adjacent_list.clear()
        self.vertex.clear()
    '''
    Vertex
    '''
    def add_vertex(self, data):
        v = Vertex(data)
        self.vertex.append(v)
    def del_vertex(self, data):
        for idx, item in enumerate(self.vertex):
            if item.data == data:
                self.vertex.pop(idx)
                return True
        return False
    '''
    Edge
    '''
    def create_edge(self, weight=0, v_from=None, v_to=None):
        return Edge(weight, v_from, v_to)
    def add_edge(self, edge):
        v_from = edge.v_from
        if 0 > v_from: return False
        self.vertex[v_from].adjacent_list.append(edge)
        return True
    def del_edge(self, idx):
        if idx < 0 or idx >= len(self.edge): return False
        self.edge.pop(idx)
        return True
~~~

* test
~~~
g = Graph()
g.add_vertex(1)
g.add_vertex(2)
g.add_vertex(3)
g.add_vertex(4)
g.add_vertex(5)
g.add_vertex(6)
g.add_vertex(7)

g.add_edge(g.create_edge(10, 0, 1)) # 1 -> 2
g.add_edge(g.create_edge(10, 0, 2)) # 1 -> 3
g.add_edge(g.create_edge(10, 1, 3)) # 2 -> 4
g.add_edge(g.create_edge(10, 1, 4)) # 2 -> 5
g.add_edge(g.create_edge(10, 2, 3)) # 3 -> 4
g.add_edge(g.create_edge(10, 2, 5)) # 3 -> 5
g.add_edge(g.create_edge(10, 3, 4)) # 4 -> 5
g.add_edge(g.create_edge(10, 3, 6)) # 4 -> 7
g.add_edge(g.create_edge(10, 4, 6)) # 4 -> 5
g.add_edge(g.create_edge(10, 5, 6)) # 4 -> 5

g.show_graph()

g.del_graph()

g.show_graph()
~~~

* result
~~~
***** Print graph *****
0 :1[10]2[10]
1 :3[10]4[10]
2 :3[10]5[10]
3 :4[10]6[10]
4 :6[10]
5 :6[10]
6 :
***** Print graph *****
~~~
