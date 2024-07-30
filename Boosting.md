## Bagging 透過隨機抽樣的方式生成每一棵樹，最重要的是每棵樹彼此獨立並無關聯
## Boosting 則是透過序列的方式生成樹，後面所生成的樹會與前一棵樹相關
## 1. AdaBoost
## 原理
1. 先假設每個資料點權重皆相同
2. 找出錯誤點並帶入公式 (1 - ε(error rate) / ε)^1/2 * w，使錯誤點的權重提高，正確的點 w 則除以 (1 - ε(error rate) / ε)^1/2 
3. 再根據加權後權重進行判斷，並重複執行
4. 最後在根據樹的 ε 計算出不同樹的權重 a = ln (1 - ε(error rate) / ε)^1/2 
5. 根據權重，所有數進行多數投票制
## Python Package
1.      from sklearn.ensemble import AdaBoostClassifier
2.      from sklearn.tree import DecisionTreeClassifier
3.      model = AdaBoostClassifier(base_estimator=DecisionTreeClassifier())
4.  Parameters :
     * n_estimators ： 樹的數量。
     * learning_rate : ε
     * base_estimator ： 通常是決策樹
## 2. XGBoost
## 原理
1. 先進行基本預測，再來隨機取特徵與資料量，計算資料與預測的殘差(R)，建構第一顆樹
2. 計算各節點 Similarity Scores = ΣR^2 / (殘差的數量 + λ(正則化參數))、Gain = Σ 分裂後葉子的 Similarity Scores - 根的Similarity Scores
3. 藉由 gammea 來修剪樹，如果 (Gain - Gamma) < 0 即修剪該分支
4. 計算各節點 Output Values = ΣR / (殘差的數量 + λ) 
5. 各點預測值 = 基本預測值 + ε(Learning Rate) * Output Values
6. 預測值持續計算新增新樹的 Output Values ，直到與資料殘差殘差極小或零為止
## Python Package
1.       import xgboost as xgb
2.       model = xgb.XGBClassifier
3. Parameters :
     * n_estimators ： 樹的數量。
     * learning_rate : ε
     * max_depth ： 樹的最大深度。
     * subsample ： 訓練每棵樹的樣本比例
     * colsample_bytree ： 訓練每棵樹的特徵比例
## 3. Catboost
## 原理與 XGBoost 相同
## 優勢
1. 能自動處理類別型特徵與缺失值
2. 可以處理各種數據類型，如音頻、圖像
3. 減少人工調參的需要，並降低了過擬合的機率
## Python Package
1.       from catboost import CatBoostClassifier
2. Parameters :
     * iterations ： 樹的數量。
     * learning_rate : ε
     * depth ： 樹的最大深度。
     * cat_features = 類別型特徵列索引

## Reference
https://ithelp.ithome.com.tw/users/20107247/articles?page=5
