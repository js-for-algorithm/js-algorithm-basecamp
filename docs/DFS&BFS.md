# 탐색 알고리즘 DFS/BFS
## 그래프(Graph) 탐색이란?
> 하나의 노드를 시작으로 다수의 노드를 방문하는 것

-> 두 노드는 인접하다(Adjacent) = 두 노드가 간선으로 연결되어 있다.
### 그래프 기본 구조
1. 노드(Node)와 간선(Edge)으로 표현된다.(이때 노드는 정점(Vertex)이라고도 말한다.)
2. 그냥 지하철 노선도에서 각각 역을 노드, 역을 이은 노선을 간선이라고 생각하면 쉬울 듯 하다.(나만 그런가)

### 인접 행렬 vs 인접 리스트
정의)
1. 인접 행렬(Adjacency Matrix) : 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식
2. 인접 리스트(Adjacency List) : 리스트로 모든 노드에 연결된 노드를 차례대로 연결된 형태를 기록하는 방식

차이점)
1. 메모리 측면 : 인접 리스트가 더 효율적
2. 속도 측면 : 인접 행렬이 더 빠름

## DFS란(Depth-First Search, 깊이 우선 탐색)
> 그래프에서 깊은 부분을 우선적으로 탐색하는 알고리즘

-> 특정한 경로로 탐색하다가 특정한 상황에서 최대한 깊숙이 들어가서 노드를 방문한 후,
다시 돌아가 다른 경로로 탐색한다.

### DFS의 동작 과정
> 스택 자료구조를 이용함

1. 탐색 시작 노드를 스택에 삽입하고 방문 처리(스택에 한번 삽입 처리된 노드의 재삽입 방지를 위해 체크하는 것)를 한다.
2. 여기서 스택의 최상단 노드에 방문하지 않은 인접 노드의 유무에 따라 달라진다.<br/>
2-1. 방문하지 않은 인접 노드가 있다면? 그 인접 노드를 스택에 넣고 방문 처리를 한다.<br/>
2-2. 방문하지 않은 인접 노드가 없다면? 스택에서 최상단 노드를 꺼낸다.<br/>
3. 2번 과정(정확히는 상황에 따라 2-1번 or 2-2번)을 더 이상 수행할 수 없을 때까지 반복한다.

### DFS의 특징
1. 구현이 간단하다.(스택 자료구조에 기초함)
2. 탐색 수행에 있어서 데이터의 개수가 N개인 경우 시간복잡도는 O(N)
3. 실제 구현을 재귀 함수로 구현했을 경우 매우 간결하다.

## BFS란(Breadth First Search, 너비 우선 탐색)
> 가까운 노드부터 탐색하는 알고리즘

### BFS의 동작 과정
> 큐 자료구조를 이용함
1. 탐색 시작 노드를 큐에 삽입하고 방문 처리(스택에 한번 삽입 처리된 노드의 재삽입 방지를 위해 체크하는 것)를 한다.
2. 큐에서 노드를 꺼내 해당 노드의 인접 노드 중에서 방문하지 않은 노드를 모두 큐에 삽입하고 방문 처리를 한다.
3. 2번 과정을 더 이상 수행할 수 없을 때까지 반복한다.

### BFS의 특징
1. 구현이 간단하다.(큐 자료구조에 기초함)
2. 탐색 수행에 있어서 시간복잡도는 O(N)
3. 일반적인 경우 DFS보다 조금 더 빠르게 동작한다.