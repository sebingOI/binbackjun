# 9625(BABBA)

> 문제 설명
> 

상근이는 길을 걷다가 신기한 기계를 발견했다. 기계는 매우 매우 큰 화면과 버튼 하나로 이루어져 있다.

기계를 발견했을 때, 화면에는 A만 표시되어져 있었다. 버튼을 누르니 글자가 B로 변했다. 한 번 더 누르니 BA로 바뀌고, 그 다음에는 BAB, 그리고 BABBA로 바뀌었다. 상근이는 화면의 모든 B는 BA로 바뀌고, A는 B로 바뀐다는 사실을 알게되었다.

버튼을 K번 눌렀을 때, 화면에 A와 B의 개수는 몇 개가 될까?

> 전체 코드
> 

```lua
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString();

let K = parseInt(input)
let A = 1;
let B = 0;
for (let i = 0; i <K; i++){
  let temp = A;
  A = B
  B = temp + B
}
//다음 단계로 넘어갈때는 A는 B로 , B는 AB로 바뀌니까
//지금 단계의 B 갯수만큼 다음 A가 되고 
//지금 단계의 A+B를 한게 다음 B

console.log(A +' '+ B)
```

> 코드 설명
> 
1. require()을 사용하여 fs 모듈을 불러온 후, fs 변수에 저장합니다.
2. fs 모듈의 readFileSync()를 사용하여 파일을 동기적으로 불러온 후, toString()을 사용하여 문자열 요소로 갖는 배열을 생성하여 input 변수에 저장합니다.
3. 변수 K에 parseInt()를 사용하여 input을 정수로 형변환 하여 저장합니다.
4. 변수 A 에 1을 저장합니다
5. 변수 B 에 0을 저장합니다.
6. for문을 K 만큼 카운트 합니다
7. temp 변수를 사용하여 A를 저장하게 합니다.
8. A 에 B 를 저장합니다
9. B 에 temp 와 B를 저장합니다
10. 다음 단계로 넘어 갈때는 A 는 B로 , B는 AB로 바뀌기 때문에 지금 단계의 B 갯수만큼 다음 A가 되고 지금 단계의 A+B를 한 값이 다음 B가 되는 것입니다.