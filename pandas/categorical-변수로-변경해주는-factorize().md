# categorical 변수로 변경해주는 pd.factorize() 함수

---
input으로 들어온 값을 범주형 변수로 인코딩합니다.

이 방법은 배열의 모든 원소들이 고유한 값을 가지고 있을 때 숫자 표현으로 변경하는데 유용합니다.

`sort`가 `ture`일 경우 unique한 값이 정렬되고 인코딩시 숫자에도 반영됩니다.

`factorize`는 `pandas.factorize()`와 `Series.factorize()` 및 `Index.factorize()`로 사용할 수 있습니다.

```
codes, uniques = pd.factorize(['b', 'b', 'a', 'c', 'b'], sort=True)
codes
# array([1, 1, 0, 2, 1])
uniques
# array(['a', 'b', 'c'], dtype=object)
```
