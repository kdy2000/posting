### nth_element (STL)
배열에서 k번째 수를 얻고 싶으면,

1. 정렬(nlogn) 후 k번째 수를 찾는다.
2. quick selection 등을 사용하여, k번째 수를 찾는다.

이렇게 2가지가 있다. quick sort를 복습하고, 추가적으로 quick selection 등을 알아보았었다. *(구현은 귀찮아서 머리로만 하고 끝냈다. 어차피 nth_element 쓸것이기도 하고, 시간도 넉넉치 않다. 나중에 divide & conquer 구현력 올리고 싶을때 타이핑 해보자.)*

quicksort, quickselection등은 발상을 위해서라도 어떤 개념인지는 알고 가야한다. 이제 개념을 공부했으면, nth_element를 사용해보자. (시간복잡도는 대강 O(n), 여기에 상수가 더 붙기도 하고, 정말정말 worst 라면 $n^{2}$까지 간다고 한다....)

```c
o <- 정렬되지 않은 배열, 0 base
nth_element(o, o+k-1, o+n);
printf("%d\n", o[k-1]);
```
```c
o <- 정렬되지 않은 배열, 1 base
nth_element(o+1, o+k, o+1+n);
printf("%d\n", o[k]);
```
```c
vector<int> o;
nth_element(o.begin(), o.begin() + k-1, o.end());
printf("%d\n", o[k-1]);
```