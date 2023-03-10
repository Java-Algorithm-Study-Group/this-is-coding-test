# [1이 될 때까지](https://github.com/Java-Algorithm-Study-Group/this-is-coding-test/blob/main/seungjun/src/greedy/Example4.java)

## 문제

어떠한 수 N이 1이 될 때까지 다음의 두 과정 중 하나를 반복적으로 선택하여 수행하려고 한다.<br>
단, 두번째 연산은 N이 K로 나누어 떨어질 때만 선택할 수 있다.

1. N에서 1을 뺀다.
2. N을 K로 나눈다.

**Input**

첫째줄에 N(2 <= N <= 100000)과 K(2 <= K <= 100000)가 공백으로 구분되며 각각 자연수로 주어진다. 이 때 입력으로 주어지는 N은 항상 K보다 크거나 같다.

```
25 5
```

**Output**

첫째줄에 N이 1이 될 때까지 1번 혹은 2번의 과정을 수행해야 하는 횟수의 최솟값을 출력한다.

```
2
```

## 해설

이 문제의 포인트는 **최대한 많이 나누기**이다.<br>
따라서 나누어 떨어지 않으면 1번 연산을 반복한 후 2번 연산을 하면 된다.<br>
다만 매번 % 연산 결과를 비교하고, 연산 방식을 선택하는 것은 효율적이지 않다.<br>
그래서 포인트를 하나 더 집어보면 **N을 K로 나눈 나머지는 곧 1을 뺀 연산이 동작한 횟수를 의미한다**는 것이다.<br>
그래서 1번 연산을 반복할 필요 없이 % 연산을 통해 한번에 해결할 수 있다.<br>
결과적으로 아래와 같은 과정을 반복하면 된다.

1. N % K => 1번 연산을 반복한 횟수
2. (N - (N % K)) / K => 1의 결과를 K로 나눈 몫

마지막으로 1, 2 과정 중 N < K이면, 반복문을 나온 뒤 N이 1이 될 때까지 1번 연산을 반복하는 횟수인 N - 1을 추가하면 된다.