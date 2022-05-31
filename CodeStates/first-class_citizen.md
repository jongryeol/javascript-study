일급객체
1. 변수에 할당 가능
let 변수 = function(){}

function 변수2 (){}

console.log(변수2())
console.log(변수2)

2. 다른 함수의 전달인자로 전달 가능
function a (func/*콜백함수*/, num){}
함수의 전달인자로 전달된 함수를 콜백함수라고 한다

3. 다른 함수의 결과로서 리턴 가능
let add =function (num1){
    return function (num2){
        return num1 + num2
    }
}
// 클로저함수 == 커링 함수(함수를 리턴하는 함수)


=> 문자열, 숫자 같은 다른 데이터처럼 사용 가능
=> 자바스크립트에서 함수는 일급객체


고차함수 
 배열 내장 메서드
 * 메서드 : 함수 == 메서드(map,,,)
 Array.prototype.map ... //객체지향에서 배움
 prototype : 원형 객체

 1. map
배열의 각 요소애 콜백 함수를 적용시킨 새로운 배열을 리턴해준다
let arr = [1,2,3,4,5]

function multiply2 (num) {
    return num * 2
}

arr.map(multiply2);
// [2,4,6,8,10]

1 > map > 2
2 > map > 4
3 > map > 6
[multiply2(1), multiply2(2) ... ]

 2. filter
배열의 각 요소애 콜백 함수를 적용시켰을 때, true를 리턴하는 요소들만 모은 새로운 배열을 리턴

 3. reduce
배열의 각 요소를 콜백함수에 맞게 하나로 응축시킨 값을리턴
(초기값), 누적값, 현재값

let arr = [1,2,3,4,5]

arr.reduce ( function (acc, cur) {
    return acc + cur
}, 10 /*초기값*/)

// if 초기값이 없다면, 초기값 === 누적값
// 1(acc) + 2(cur) = 3
// 3(acc) + 3(cur) = 6
// 6(acc) + 4(cur) = 10
// 10(acc) + 5(cur) = 15

// if 초기값이 았다면, 초기값 === 초기값
// 10(acc) + 1(cur) = 11
// 11(acc) + 2(cur) = 13
// 13(acc) + 3(cur) = 16
// 16(acc) + 4(cur) = 20
// 20(acc) + 5(cur) = 25

 4. 기타

일급객체
함수가 일급객체라서 고차함수로 활용 가능