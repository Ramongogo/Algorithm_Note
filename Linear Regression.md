## 找出一條直線使 MSE 最小
## 原理
1. 假設三點為 (1,1), (2,3), (3,4)
2. 先寫成a + b = 1, a + 2b = 3, a+ 3b = 4
3. 後轉換成矩陣的寫法
4. 對等式乘以等式左邊矩陣的轉至矩陣
5. 再乘以等式左邊的反矩陣
6. 得出 (a,b) 為 (-0.33, 1.5)
## Python 程式碼
1.     from sklearn.metrics import mean_squared_error
2.     linearModel = LinearRegression()
3.     linearModel.fit(X, y)
4. Parameters :
   * fit_intercept : 是否有截距，如果沒有則直線過原點。
5. Attributes :
    * coef_ : 取得係數。
    * intercept_ : 取得截距。
## 多項式回歸
**使用 make_pipeline 將 PolynomialFeatures 與 LinearRegression 整合成一個多項式回歸模型**
1.     from sklearn.linear_model import LinearRegression
2.     from sklearn.preprocessing import PolynomialFeatures
3.     from sklearn.pipeline import make_pipeline
4.     def PolynomialRegression(degree=2, **kwargs):
         return make_pipeline(PolynomialFeatures(degree), LinearRegression(**kwargs))
        // degree是維度的程度, **kwargs允許使用LinearRegression的參數
5.     for degree in [1,3,9]:
         y_test=PolynomialRegression(degree).fit(X,y).predict(x_test)
       // 檢測不同維度下的擬合程度
