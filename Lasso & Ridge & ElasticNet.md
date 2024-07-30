## Lasso 為 Linear Regression 加上 L1， Ridge 是加上 L2， ElasticNet 加上L1與L2綜合懲罰項
## 增加了對迴歸權重大小的懲罰值，避免over-fitting
## Lasso 
* L1 norm的效果可以使不重要的變數係數變為 0 ，當特徵減少，即達成變數篩選，用來預測的準確度就可以比較穩定
## Ridge
* 當都是重要的特徵，可以處理多元共線性問題，但 Ridge 並不能使估計出的係數為 0，所以無法做變數篩選
## ElasticNet
* 可適用在覺得不是每個特徵都是非常重要的特徵但同時也不想要像 Lasso 有那麼強的特徵篩選功能
## Python Package
### Lasso
1.     from sklearn.linear_model import Lasso
2. Parameters :
     * alpha : 決定正則化強度
### Ridge
1.      from sklearn.linear_model import Ridge
2.  Paramters :
     * alpha
### ElasticNet
1.      from sklearn.linear_model import ElasticNet
2.  Paramters :
     * alpha
     * l1_ratio

## Reference
https://ithelp.ithome.com.tw/users/20107247/articles?page=5
