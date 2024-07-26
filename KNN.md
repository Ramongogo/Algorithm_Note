## 根據資料點之間的距離來進行分類，距離哪一種類別最近該資料點就會被分到哪類
## 原理
1. 假如有一筆資料 x ，KNN 會依據設定的 k 值在資料中尋找k個距離相近的資料點，並將x的類別預測為數量最多的那個類別。 
// k一般為奇數
2. 距離計算方式 :
     * 明氏距離 : d = (Σ( x - y)^p)^1/p
     * 曼哈頓距離 : d = Σ | x - y |
     * 歐幾里德距離 : d = (Σ( x - y)^2)^1/2
## Python 程式碼
1.      from sklearn.neighbors import KNeighborsClassifier, KNeighborsRegressor
2.  Parameters :
      * n_neighbors：k的值
      * weights：鄰居權重
          * uniform : 所有鄰居權重相等
          * distance：權重與距離成反比
          * p : 明氏距離的p值
