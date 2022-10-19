# testResult
## ===입력===
![image](https://user-images.githubusercontent.com/88232976/196567894-c6001fdd-ce20-4386-a448-750f27aff941.png)
## ===출력===
전체 학생의 성적 평균을 구하고 평균미만은 불합격 성적 이상은 합격으로 표시
(내림차순으로 표시)   
![image](https://user-images.githubusercontent.com/88232976/196568279-4434b098-1ec6-47b7-bf96-1ee95eea6958.png)   
성적 10점을 '=' 로 표시(반올림)   
![image](https://user-images.githubusercontent.com/88232976/196568455-62aff37a-9409-453f-b181-2edd2f54c023.png)   

전체 출력   
![image](https://user-images.githubusercontent.com/88232976/196567919-a2b13518-b4c7-4c74-a27e-ac94162d50b3.png)   

``` C
#include <stdio.h>

int main() {
	int a[10];
	double aver = 0;
	int temp[10] = {0,};
	for (int i = 0; i < 10; i++) {
		printf("%d 번째 학생에 성적은?  ",i+1);
		scanf_s("%d",&a[i]);
		aver += a[i];
	}
	aver /= 10.0;
	printf("\n전체학생의 평균은 %f \n", aver);
	for (int i = 0; i < 10; i++) {
		for (int j = i + 1; j < 10; j++) {
			if (a[i] < a[j]) {
				temp[i]++;
			}
			else {
				temp[j]++;
			}
		}
	}

	for (int i = 0; i < 10; i++) {
		for (int j = 0; j < 10; j++) {
			if (temp[j] == i) {
				printf("학생 %d :", j+1);
				if (aver <= a[i]) {
					printf("합격\n");
				}
				else {
					printf("불합격\n");
				}
			}
		}
	}
	for (int i = 0; i < 10; i++) {
		
		int b;
		//반올림 x
		printf("\n학생%d :", i+1);
		if ((a[i] % 10) < 5) {
			b = a[i] / 10;
		}
		// 반올림 o
		else {
			b = (a[i] / 10) + 1;
		}
		for (int j = 0; j < b; j++) {
			printf("=");
		}

	}
	return 0;
}
```
