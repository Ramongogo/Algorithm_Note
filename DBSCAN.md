## 依據密度性質自行決定最終分群的數量
## 原理
1. ε (eps)，由這個參數值為半徑劃出的圓型區域稱為 ε-鄰域
2. minPts，構成高密度區域需要最少有幾個點
3. 如果該點的 ε 具 minPts，即設為核心點並建立連結線，如果少於 minPts 就非核心點並不產生連結線
4. 雙邊連結即為同一群，而如果被同群的 ε 概括，但此些點並未具 minPts ，則分為同一群
## Python Package
1.      from sklearn.cluster import DBSCAN
2.  Parameters :
     * eps : ε值
     * min_samples： minPts值

## Reference
https://ithelp.ithome.com.tw/users/20107247/articles?page=5
