## 找到一條直線將資料做分類
## 原理
1. 利用 sigmoid function { f(x) = 1 / 1 + e^-X } 將輸出轉換成 0~1 的值，表示可能為這個類別的機率值 // x為任意方程式
2. 假設 P 代表事件會發生的機率，P = 1 / 1 + e^-X，整理後可得 e^X / 1 + e^X
3. 事件不會發生的機率則為 1 - P， 也等於 1 / 1 + e^X
4. 再求出 Odds = P / 1 - P = e^x
5. 取 log 後 ln(P / 1 - P) = x
6. 用最大概似法求出 x 的係數值
7. 再帶入 sigmoid function 求出 P
## Python Package
1.      from sklearn.linear_model import LogisticRegression
2.  Parameters :
     * penalty : 正規化 l1 / l2 ，防止模型過度擬合
     * solver： 用於優化的算法
       * newton-cg
       * lbfgs
       * liblinear
       * sag
       * saga
    * C : 正則化的強度
