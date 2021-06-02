# Sorted - 딕셔너리 안에 딕셔너리 정렬하기

---

```python
x = {66: {'score': 0.707},
     68: {'score': 0.541},
     72: {'score': 0.574},
     73: {'score': 0.651},
 100027: {'score': 0.432},
 100028: {'score': 0.541}}
 ```

데이터가 다음과 같이 있는 상태에서 어떻게 score가 낮은
순서대로 key값을 정렬할 수 있을까?

간단하게 `sorted`를 사용할 수 있다.



```python
sorted(x.keys(), key=lambda i:x[i]['score'])
# [100027, 68, 100028, 72, 73, 66]
```

아주 야무지게 정렬됨을 볼 수 있다.

```python
sorted(x.keys(), key=lambda i:x[i]['score'], reverse=True)
# [66, 73, 72, 68, 100028, 100027]
```

큰 순서대로 정렬하고 싶으면 `reverse=True`를 사용하면 된다.