# Algorithms-Library

## Dijkstra.py
非負重み付き無向連結グラフ $G=(V, E)$ における単一始点最短経路問題を Dijkstra 法を用いて解く。  
最短経路のコストおよび経路復元を行う関数を実装。  
計算量： $O((E+V)\mathrm{log}V)$

## Prim.py
重み付き無向連結グラフ $G=(V, E)$ における最小全域木 (Minimum Spanning Tree) を Prim 法を用いて求める。  
最小全域木のコストおよび最小全域木を構成する辺の集合を求める関数を実装。  
計算量： $O(E\mathrm{log}V)$

## Kruskal.py
重み付き無向連結グラフ $G=(V, E)$ における最小全域木 (Minimum Spanning Tree) を Kruskal 法を用いて求める。  

## Union_Find.py
Union-Find は、根付き木を利用して要素を素集合(互いに重ならない集合)に分割・管理するデータ構造である。  
Union-Find では以下の 2 つの操作を高速に行える。ただし集合の分割はできない。  
計算量: $O(\alpha(n))$ (ただし $\alpha(n)$ はアッカーマン関数 $A(n,n)$ の逆関数で log より小さい)

**判定**  
ある要素がどの集合(グループ)に属しているか判定する。2 つの要素が同じグループに属しているかも判定可能。  
根付き木を上向きに辿り、その要素が含まれるグループの根を調べる。同じ根に辿り着けば同じグループに属する要素ということになる。また、一度根を辿ったら、その際に経由したすべてのノードを根に向かって張りなおすことで計算時間が大幅に短縮できる(経路圧縮)。

**併合**  
2 つの集合を 1 つに合併する。  
片方のグループの木の根からもう片方のグループの木の根に辺を張れば、二つの木が一つの木になり、併合される。このとき、二つの木のランクが異なる場合は、ランクの小さい木から大きい木へ辺を張ることで偏りを抑えられる。この処理を実現するためには、各木のランクを記憶しておく必要がある。