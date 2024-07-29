## 非監督式學習，用來分群
## 原理
1. 決定 k 值（分成 k 群）
2. 隨機給定 k 個 cluster centroid (群心)
3. 計算每個樣本與每個群心之距離，並將樣本歸類分配給距離最近的群心
4. 通過分配給每個先前群心的所有樣本的平均值重新計算新群心
5. 重複步驟3與步驟4，直到群心不再有大的變動
## Python Package
1.      from sklearn.cluster import KMeans
2.  Parameters :
     * n_clusters : k 的值
     * max_iter : 單次運行迭代次數
     * tol：如果在一个迭代中，群心的位移小於這個值，算法將提前結束
     * n_init：運行算法的次數，計算最佳為結果
