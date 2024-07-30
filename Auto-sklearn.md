## Auto-sklearn 採用元學習 (Meta Learning) 貝葉斯優化 (Bayesian Optimization) 與自動整合 (Ensemble Selection) 的架構在有限時間內搜尋最佳的模型
## 原理
1. 元學習
   *  參考了 OpenML 140 個資料集，並彙整了 38 個元特徵
   *  使用貝葉斯優化進行模型訓練，並將這些資料集對應的模型與最佳的超參數儲存起來
   *  資料透過元特徵進行相似度匹配
2. 貝葉斯優化
   * Data Pre-processors
      * 特徵縮放
      * 填補缺失值
      * one-hot encoding
      * 類別資料不平衡
   * Feature Pre-processors
      * PCA
      * linear svm
      * 總計12種選一種使用
3. 整合學習
   * Bagging
## Python Package
1.       from autosklearn.experimental.askl2 import AutoSklearn2Classifier
2. Parameters :
   * time_left_for_this_task: 搜尋時間(秒)，預設3600秒(6分鐘)
   * per_run_time_limit: 每個模型訓練的上限時間，預設為搜尋時間的1/10
   * ensemble_size: 模型輸出數量，預設50
   * resampling_strategy: 資料採樣方式。為了避免過擬合，可以採用交叉驗證機制。預設為 holdout
3.       automlclassifierV2.leaderboard(detailed = True, ensemble_only=True) // 檢視各模型權重

## Reference 
https://ithelp.ithome.com.tw/users/20107247/articles?page=5
