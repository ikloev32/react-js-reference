# react-js-reference


# 1. 구성요소
ES6클래스를 사용하여 정의된 구성 요소를 사용하는 기본 클래스로 컴포넌트를 사용하여 UI를 독립적이고 재사용 가능한 부분으로 분리하고 각 부분을 개별적으로 분리한다

- React.Component
- React.PureComponent

## 1-1. React.Component

## 1-1-1 . 개요
React.Component 는 추상 클래스로 직접 참조가 불가능하다. 그래서 상속을 받아 render() 메소드를 정의 한다

*react 구성 요소는 일반 javascript class 로 정의 한다

```JSX
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```    
### 생명 주기 ( Life Cycle )
각 구성 요소에는 프로세스의 특정 시간에 코드를 실행하기 위해 재정의 할 수있는 여러 "라이프 사이클 메소드"가 있다. 접두사가 붙은 메소드 will는 무언가가 일어나기 바로 전에 호출되며 접두사가 붙은 메소드 did는 무언가가 발생한 직후에 호출된다.

## 1-2. React.PureComponent
React.PureComponent정확히 같지만 얕은 소품과 상태 비교를 React.Component 구현 shouldComponentUpdate()합니다.
React 구성 요소의 render()함수가 동일한 소품 및 상태에서 동일한 결과를 렌더링하는 React.PureComponent경우 일부 경우 성능 향상을 위해 사용할 수 있다 .

# 2. 요소 만들기

JSX 를 사용 하여 UI의 모양을 설명하는 것이 react 에서 권장 하는 방식이다. 일반적으로 JSX를 사용하는 경우 다음 메소드를 직접 호출하지 않는다.

- createElement()
- createFactory()

###  * JSX란?

js + xml 를 합쳐서 탄생한 자바스크립트의 확장 문법으로 개발자가 자바스크립트 내부에 마크업 코드를 작성해 줄 수 있게 해줍니다.
단순히 XML만 아니라 변수나 프로퍼티의 바인딩 기능도 제공한다

## JSX 를 사용 해야 하나 

꼭 사용 해야 하는것은 아니다. JSX로 수행 할 수있는 작업은 일반 자바 스크립트로도 수행 할 수 있다.

## JSX를 사용 할 경우

        class Hello extends React.Component {
          render() {
            return <div>Hello {this.props.toWhat}</div>;
          }
        }

        ReactDOM.render(
          <Hello toWhat="World" />,
          document.getElementById('root')
        );
        
## JSX를 사용 하지 않을 경우
사용 하지 않을경우 아래 와 같은 함수들을 사용한다

## 2-1. createElement()

        class Hello extends React.Component {
          render() {
           return React.createElement('div', null, `Hello ${this.props.toWhat}`);
          }
        }

        ReactDOM.render(
          React.createElement(Hello, {toWhat: 'World'}, null),
          document.getElementById('root')
        );
        
createElement 상수로 선언 하여 이런 방식으로도 사용이 가능하다

        const e = React.createElement;

          ReactDOM.render(
            e('div', null, 'Hello World'),
            document.getElementById('root')
          );

## 2-2. createFactory()
JSX를 사용 하거나 React.createElement()하거나 대신 직접 사용 하는 것이 좋다고 한다

        React.createFactory(type)


# 3. 요소 변환 하기

## 3.2 isValidElement()
  객체가 React 요소인지 확인한다. true 또는 false를 반환 한다
  
        React.isValidElement(object)
        
 

 
