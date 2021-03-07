# ch04 함수

1. 타입스크립트의 함수 또한 `function`, `() => {}`로 생성가능하다.
2. 중첩함수를 이용하여 callback을 조정할 수 있다.
3. type으로 함수의 형태를 미리 선언하여 실수를 방지할 수 있다.
4. 매개변수 또한 `age?`형태의 선택 매개변수로 선언하여 사용할 수 있다.

# 고차함수

1. 함수를 반환하는 함수를 고차함수라 한다.
2. 함수 내부에서 반환하는 함수의 최종적인 반환값을 클로저라고 한다.
3. 고차 함수에서 아직 값이 아닌 함수인 것을 부분 어플리케이션(partial application) 혹은 부분 적용 함수(partially applied function)라고 한다.

```typescript
type NumberToNumber = (number) => number;
const partial = (a: number): NumberToNumber => {
	const _partial = (b: number): NumberToNumber => {
		return a + b; //클로저
	};
	return _partial;
};
```

# 콜백함수

1. 매개변수로 전달받은 형태의 함수를 실행시키는 형식

```typescript
export const init = (callback: () => void): void => {
	console.log('default initializtion finished.');
	callback();
	console.log('all initializtion finished.');
};
```
