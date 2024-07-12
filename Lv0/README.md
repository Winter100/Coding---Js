[부분 문자열](https://school.programmers.co.kr/learn/courses/30/lessons/181842)
```js
function solution(str1, str2) {
    return str2.includes(str1) ? 1 : 0
}
```
<hr />

[부분 문자열인지 확인하기](https://school.programmers.co.kr/learn/courses/30/lessons/181843)
```js
function solution(my_string, target) {
    return my_string.includes(target) ? 1 : 0;
}
```
<hr />

[뒤에서 5등 위로](https://school.programmers.co.kr/learn/courses/30/lessons/181852)
```js
function solution(num_list) {
    return num_list.sort((a,b)=>a-b).slice(5)
}
```
<hr />

[배열의 길이에 따라 다른 연산하기](https://school.programmers.co.kr/learn/courses/30/lessons/181854)
```js
function solution(arr, n) {
    if (arr.length % 2 !== 0) {

        for (let i = 0; i < arr.length; i += 2) {
            arr[i] += n;
        }
    } else {
        
        for (let i = 1; i < arr.length; i += 2) {
            arr[i] += n;
        }
    }
    return arr;
}
```
<hr />

[배열 비교하기](https://school.programmers.co.kr/learn/courses/30/lessons/181856)
```js
function solution(arr1, arr2) {

    const len1 = arr1.length;
    const len2 = arr2.length;
    
    if(len1 !== len2){
        return len1 > len2 ? 1 : -1;
    }
    
    const sum1 = arr1.reduce((acc,cur)=>acc+cur,0)
    const sum2 = arr2.reduce((acc,cur)=>acc+cur,0)
    
    return sum1 !== sum2 ? (sum1 > sum2 ? 1 : -1) : 0
}
```
<hr />

[배열의 원소만큼 추가하기](https://school.programmers.co.kr/learn/courses/30/lessons/181861)
```js
function solution(arr) {
  const resultArray = arr.flatMap(num => Array(num).fill(num));
  return resultArray;
}
```
<hr />

[공백으로 구분하기2](https://school.programmers.co.kr/learn/courses/30/lessons/181868)
```js
function solution(my_string) {
    const words = my_string.trim().split(/\s+/);
    return words;
}
```
<hr />

[특정한 문자를 대문자로 바꾸기](https://school.programmers.co.kr/learn/courses/30/lessons/181868)
```js
function solution(my_string, alp) {
    return my_string.replaceAll(alp, alp.toUpperCase())
}
```
<hr />

[배열에서 문자열 대소문자 변환하기](https://school.programmers.co.kr/learn/courses/30/lessons/181875)
```js
function solution(strArr) {
    const newArr = [...strArr];
    return newArr.map((item,i)=>i%2===0?item.toLowerCase():item.toUpperCase())
}
```
<hr />

[할 일 목록](https://school.programmers.co.kr/learn/courses/30/lessons/181885)
```js
function solution(todo_list, finished) {
    return todo_list.filter((item, i)=>!finished[i])
}
```
<hr />

[접두사인지 확인하기](https://school.programmers.co.kr/learn/courses/30/lessons/181906)
```js
function solution(my_string, is_prefix) {
    return my_string.startsWith(is_prefix) ? 1 : 0
}
```
<hr />

[접미사인지 확인하기](https://school.programmers.co.kr/learn/courses/30/lessons/181908)
```js
function solution(my_string, is_suffix) {
    return my_string.endsWith(is_suffix) ? 1 : 0
}
```
<hr />

[글자 이어 붙여 문자열 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/181915)
```js
function solution(my_string, index_list) {
    return index_list.map((item)=>my_string[item]).join("");
}
```
<hr />

[수 조작하기 1](https://school.programmers.co.kr/learn/courses/30/lessons/181926)
```js
function solution(n, control) {
    
    let result = n;
    
    const wasd = {
        w : 1,
        s : -1,
        d : 10,
        a : -10,
    }
    
    for (const char of control){
        result = result + wasd[char]
    }
    
    return result
}
```
<hr />

[문자열의 뒤의 n글자](https://school.programmers.co.kr/learn/courses/30/lessons/181910)
```js
function solution(my_string, n) {
    return my_string.slice(my_string.length - n)
}
```
<hr />

[이어 붙인 수](https://school.programmers.co.kr/learn/courses/30/lessons/181928)
```js
function solution(num_list) {
    const a = num_list.filter((item)=>item%2===0);
    const b = num_list.filter((item)=>item%2===1);
    
    const c = a.join("")
    const d = b.join("");
    
    const result = +c + +d
    return result
}
```
<hr />

[원소들의 곱과 합](https://school.programmers.co.kr/learn/courses/30/lessons/181929)
```js
function solution(num_list) {

    const sum = num_list.reduce((acc,cur)=>acc*cur)
    const square = (num_list.reduce((acc,cur)=>acc+cur) ** 2)
    
    return sum > square ? 0 : 1
}
```
<hr />

[더 크게 합치기](https://school.programmers.co.kr/learn/courses/30/lessons/181939)
```js
function solution(a, b) {
    const ab = [a,b].join("");
    const ba = [b,a].join("");
    
    return +ab >= +ba ? +ab : +ba;
}
```
<hr />

[간단한 식 계산하기](https://school.programmers.co.kr/learn/courses/30/lessons/181865)
```js
function solution(binomial) {
    const [num1, op, num2] = binomial.split(" ");
    switch(op){
        case "+":
            return +num1+ +num2;
        case "-":
            return num1-num2;
        case "*":
            return num1*num2;
    }
}
```
<hr />

[주사위 게임 1](https://school.programmers.co.kr/learn/courses/30/lessons/181839)
```js
function solution(a, b) {
    if(a%2===1 && b%2===1){
        return (a ** 2) + (b ** 2);
    } else if( a%2===0 && b%2===0){
        return Math.abs(a-b)
    } else {
        return 2 * (a+b)
    }
}
```
<hr />

[수 조작하기 2](https://school.programmers.co.kr/learn/courses/30/lessons/181925)
```js
function solution(numLog) {
    const wasd = {
        w:1,
        s:-1,
        d:10,
        a:-10
    }

    let result = "";

    for(let i=1; i<numLog.length; i++){

        let diff = numLog[i] - numLog[i - 1];

        for(const key in wasd){
        if(wasd[key] === diff){
            result += key
            break;
            }
        }
    }
    return result
}
```

<hr />

[가까운 1 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/181898)

```js
function solution(arr, idx) {
    return arr.indexOf(1,idx)
}
```

<hr />

[9로 나눈 나머지](https://school.programmers.co.kr/learn/courses/30/lessons/181914)

```js
function solution(number) {
    return ([...number].reduce((acc,cur)=>acc+Number(cur),0) % 9)
}
```

<hr />

[0 떼기](https://school.programmers.co.kr/learn/courses/30/lessons/181847)

```js
function solution(n_str) {
    const length = n_str.length;
    
    let i = 0;
    while(i<length && n_str[i]==="0"){
        i++;
    }
    
    return n_str.slice(i)
}
```
<hr />

[접미사 배열](https://school.programmers.co.kr/learn/courses/30/lessons/181909)

```js
function solution(my_string) {

    const newArr = [];
    for(let i=0; i<my_string.length; i++){
        newArr.push(my_string.slice(i))
    }
    
    return newArr.sort()
}
```
<hr />

[날짜 비교하기](https://school.programmers.co.kr/learn/courses/30/lessons/181838)

```js
function solution(date1, date2) {
    return Number(date1.join("")) < Number(date2.join("")) ? 1 : 0
}
```
<hr />

[조건에 맞게 수열 변환하기3](https://school.programmers.co.kr/learn/courses/30/lessons/181835)

```js
function solution(arr, k) {
    if(k%2===0){
        return arr.map((num)=>num+k)
    } else{
        return arr.map((num)=>num*k)
    }
}
```
<hr />

[l로 만들기](https://school.programmers.co.kr/learn/courses/30/lessons/181834)

```js
function solution(myString) {

    const result = [];
    
    for (const char of myString){
        if(char < "l"){
            result.push("l")
        } else{
            result.push(char)
        }
    }
    return result.join("")
}
```
<hr />

[문자열 잘라서 정렬하기](https://school.programmers.co.kr/learn/courses/30/lessons/181866)

```js
function solution(myString) {
    const parts = myString.split("x");
    
    return parts.filter((v)=>v).sort()
}
```
<hr />

[글자 지우기](https://school.programmers.co.kr/learn/courses/30/lessons/181900)

```js
function solution(my_string, indices) {
    indices.sort((a,b)=>b-a);
    
    for(const i of indices){
        my_string = my_string.slice(0,i) + my_string.slice(i+1)
    }
    
    return my_string
}
```
<hr />























