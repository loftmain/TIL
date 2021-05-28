# TensorFlow에서 Dataset을 사용하는 방법

---

효율적으로 모델에 데이터를 공급하려면 입력 파이프라인을 만들어서 GPU로 들어올
데이터를 멈춰있게 하지 않아야 합니다.

Tensorflow에서는 `Dataset`이라는 built-in-API를 제공하고 있습니다. `Dataset`을
사용하면 모델에 효율적으로 데이터를 공급할 수 있습니다.

## 개요

Dataset을 사용하기 위한 시나리오는 다음과 같습니다.

1. **데이터 불러오기** : 사용하려는 데이터로부터 Dataset 인스턴스를 받습니다.

2. **Iterator(반복자) 생성하기** : 생성된 데이터를 사용해서 iterator 인스턴스를
만들어 Dataset을 반복시킵니다.

3. **데이터 사용하기** : 생성된 iterator를 사용해서 모델에 공급할 dataset으로부터
요소를 가져올 수 있습니다.


## 데이터 불러오기

먼저 dataset에 넣을 데이터가 필요합니다.

데이터셋를 불러오는 방법은 다양합니다. 하나씩 확인해보겠습니다.

### numpy에서 불러오기

numpy 배열을 tensorflow로 넣는 방식입니다.

```
# (100, 2) shape의 랜덤 벡터 생성
x = np.random.sample((100, 2))
# numpy array에 대한 Dataset 생성
dataset = tf.data.Dataset.from_tensor_slice(x)
```
