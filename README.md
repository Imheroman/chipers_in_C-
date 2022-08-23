# chipers_in_C-
각 자릿수에 있는 숫자를 하나씩 출력하는 알고리즘

```c++
#include <iostream>
#include <math.h>
using namespace std;

int main(){

	int n, m, count = 0;

	cin >> n; // 수를 입력받아준다.

	m = n; // 입력받은 변수의 자릿수를 확인하기 위하 변수.

	while(m > 10){ // 자릿수를 알아내기위한 카운트
		m /= 10;
		count++;
	}
	count++; // 1의 자리까지 포함해야하니 1번 더 카운트한다.

	int a[count];

	for(int i = 0; i < count; i++){
		int t = pow(10, count-i-1);

		if(i == 0)
			a[i] = n/t; // 제일 처음에는 그냥 현재 자릿수를 나눈 몫만 필요.

		else{
			int k = pow(10, count-i);
			a[i] = (n%k)/t; // 첫번째 자릿수를 제외하곤 나머지 자릿수들은 이미 저장한 자릿수를 포함하면 안 된다.
		}
    //    a[i] = n/t;
    //    n %= t; // 혹시나 i를 이용해 자릿수를 구분하지않고 그냥 저장하고 싶다면 조건문들을 없애고 이렇게 사용
	}

	for(int i = 0; i < count; i++)
		cout << a[i];

	cout << endl;

	return 0;
}
```
