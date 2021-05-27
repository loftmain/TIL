# pip collecting error

---

```
$ pip install torch
collecting torch
Killed
```

이런 에러 해결한 방법

```angular2html
$ pip install torch --no-cache-dir
```