# [볼링공 고르기]()

## 문제

두 사람이 서로 다른 무게의 볼링공을 고르려고 한다.<br>
각각의 무게가 적혀진 N개의 볼링공이 있을 때, 서로 다른 무게를 고를 수 있는 경우의 수를 구하라.

### Input

* 첫째 줄에 볼링 공의 개수 N(1 <= N <= 1000), 공의 최대 무게 M(1 <= M <= 10)가 공백으로 구분되어 주어진다.
* 둘째 줄에 각 볼링 공의 무게 K(1 <= K <= M)가 공백으로 구분되어 주어진다.

```
5 3
1 3 2 3 2
```
```
8 5
1 5 4 3 2 4 5 2
```

### Output

* 첫째 줄에 두 사람이 볼링 공을 고르는 경우의 수를 출력한다.

```
8
```
```
25
```

## 접근

자신을 제외한 다음 인덱스의 숫자와 비교하여 동일한 숫자가 아니라면 경우의 수에 포함한다.

```
int count = 0;
for (int i = 0; i < array.length - 1; i++) {
    for (int j = i + 1; j < array.length; j++) {
        if (array[i] != array[j]) {
            count++;
        }
    }
}
```