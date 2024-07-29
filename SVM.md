## 找到一個決策邊界(decision boundary)讓分類之間的邊界距離(margins)達到最大
## 原理
### SVM
1. 先在正超平面以及負超平面隨機找兩點 m 與 n 
2. 正超平面方程式為 : w1xm + w2xm + b = 1， 負超平面公式為 w1xn + w2xn + b = -1
3. 兩方程式相減可得 w1(xm - xn) + w2(xm - xn) = 2，整理後為 (向量 w ) * (xm - xn) = 2
4. 再假設超平面上兩點 p 與 o
5. 方程式可得 w1xo + w2xo + b = 0， w1xp + w2xp + b = 0
6. 兩式相減後可得(向量 w ) * (xo - xp) = 0，因此向量 w 垂直 xo - xp
7. 則此式 (向量 w ) * (xm - xn) = 2 會等於 |xm - xn| * cosθ * |向量 w| = 2
8. |xm - xn| * cosθ = L，為 |xm - xn| 投影到 (向量 w ) 的長度，也就是邊界長度
9. L = 2 / |(向量 w )|
### SVR
* 在 SVR 中，目標是找到一條平滑的回歸線，使得大多數數據點都落在距離該線 ε 範圍內的區間內。 ε = 不敏感區間, 類似svm邊界距離
## Python Package
1.      from sklearn.svm import SVC, SVR
2. Parameters :
      * C(懲罰參數) : 限制模型的複雜度，防止過度擬合
      * kernel :
        * linear：線性核
        * poly：多項式
        * rbf：徑向基核（高斯核）
        * sigmoid：sigmoid 核
      * degree : 如果核函數為 'poly'，此參數為多項式的度數。
      * gamma : 適用於 'rbf'、'poly' 和 'sigmoid' 核，控制單個訓練樣本的影響範圍
        *  scale（1 / (n_features * X.var())）
        *  auto（1 / n_features）
