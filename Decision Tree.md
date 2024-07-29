## 據資料找出合適的規則，其目的使每一個決策能夠使訊息增益最大化
## 原理
1. 依靠亂度作為評估指標，每次決策都要使亂度最低
2.  決策亂度評估指標 ： 數值越大亂度越高，分類一致時亂度為零
      * Information gain (資訊獲利 ： 計算 Entropy 熵)
      * Gini Impurity (吉尼不純度 : 計算 Gini)
3. 熵公式 ： -ΣP * log2 P，資訊獲利公式 : -P * log2 P - q * log2 q // P為是的機率，q為否
4. Gini 公式 : 1 - ΣP^2，Gini Impurity公式 : 1 - (P^2 + q^2)
## Python 程式碼
1.      from sklearn.tree import DecisionTreeClassifier
2.  Parameters :
     * criterion : 亂度的評估標準
       * Gini
       * Entropy
     * max_depth :樹的最大深度
     * splitter : 特徵劃分點選擇標準
       * best
       * random
     * random_state : 亂數種子，確保每次訓練結果都一樣
     * min_samples_split : 至少有多少資料才能再分
     * min_samples_leaf : 分完至少有多少資料才能分
