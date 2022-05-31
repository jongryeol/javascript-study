# 클래스와 인스턴스
class : 모델이 되는 큰 청사진(blueprint)
instance : 청사진을 바탕으로 한 객체를 만드는 것

## 클래스 생성
```javascript
class Car {
  constructor (brand, name, color) {
    this.brand = brand;
    this.name = name;
    this.color = color;
  }
  
  drive() {
    console.log (this.name + '가 운전을 합니다');
  }
}
```
> ES6
```javascript
function Car(brand, name, color) {
  this.brand = brand;
  this.name = name;
  this.color = color;
}

Car.prototype.dirve = function() {
  console.log (this.name + '가 운전을 합니다');
}
```
> ES5

## 인스턴스 생성
```javascript
let avante = new Car('현대', '아반떼', '블랙');
let sonata = new Car('현대', '소나타', '화이트');
```
new라는 키워드를 앞에 붙이고 정의한 해당 클래스명을 뒤에 붙이면 인스턴스 객체가 생성된다.
생성된 인스턴스 객체는 class의 고유한 속성과 메소드를 가지게된다.
여기서 뒤의 파라미터들은 class를 정의할 때 설정했던 파라미터로 그대로 넘어간다.

***

## super 을 통한 상위 클래스 호출
```javascript
class Cat {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

class Lion extends Cat {
  speak() {
    super.speak();
    console.log(`${this.name} roars.`);
  }
}

let l = new Lion('Fuzzy');
l.speak();
// Fuzzy makes a noise.
// Fuzzy roars.
```
```javascript
class AppleDevice {
  constructor(manufacturingCompany, Ceo, location){
    this.manufacturingCompany = 'Apple';
    this.Ceo = 'Tim Cook';
    this.location = 'USA'
  }
}

class Iphone extends AppleDevice {
  constructor(manufacturingCompany, Ceo, location, verson, price){
  super(manufacturingCompany, Ceo, location)
  this.verson = '13'
  this.price = '$1000000'
}