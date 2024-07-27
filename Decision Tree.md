## 據資料找出合適的規則，其目的使每一個決策能夠使訊息增益最大化
## 原理
1. 11
## Python 程式碼
1.      from sklearn.tree import DecisionTreeClassifier
2.  Parameters :
     * criterion : 評估切割點指標，
       * mse
       * friedman_mse
       * mae
     * max_depth :樹的最大深度
     * splitter : 特徵劃分點選擇標準
       * best
       * random
     * random_state : 亂數種子，確保每次訓練結果都一樣
     * min_samples_split : 至少有多少資料才能再分
     * min_samples_leaf : 分完至少有多少資料才能分
