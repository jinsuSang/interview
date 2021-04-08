# interview questions

## 1. 다른 언어에 비해 Golang을 사용하면 어떤 이점이 있습니까?

- 학문적 실험으로 시작된 다른 언어들과는 달리, Golang은 실용적으로 고안되었습니다. 모든 기능 및 구문 결정은 프로그래머가 보다 쉽게 사용할 수 있도록 설계되었습니다.

- Golang은 동시성에 최적화되어 있으며 규모에 맞게 작동합니다.

- Golang은 종종 단일 표준 코드 형식 때문에 다른 언어보다 더 읽기 쉬운 것으로 여겨집니다.

- 자동 가비지 수집은 프로그램과 동시에 실행되기 때문에 Java나 Python보다 훨씬 효율적입니다.

## 2. 문자열 리터럴이란 무엇입니까?

문자열 리터럴은 문자를 연결하여 형성된 문자열 상수입니다.

raw 문자열 리터럴은 UTF-8 문자로 채워집니다. 해석된 문자열 리터럴은 일반적으로 문자열로 간주되며, 큰따옴표로 작성되고 새로운 줄과 완료되지 않은 큰따옴표를 제외한 모든 문자를 포함합니다.

## 2-1 Golang에서 문자열 리터럴이란?

Go 언어의 소스 코드는 UTF-8로 되어 있습니다. 코드 상에 표시된 문자열도 UTF-8로 인코딩되어 있습니다. char는 1바이트, rune은 int32 32비트 정수의 별칭입니다.

## 2-2 배열과 슬라이스

배열은 크기가 자료형에 고정되어 있습니다. 반면 슬라이스는 길이와 용량을 갖고 있고 길이가 변할 수 있는 구조입니다. 슬라이스는 연속된 메모리 공간을 활용하는 것이라서 용량 제한이 발생합니다. 용량 제한이 발생하면 그 크기에 맞는 메모리를 재할당합니다. 슬라이스는 배열을 가리키고 있는 구조체라고 볼 수 있습니다.

for - range문을 사용해 문자열을 반복하면 문자열 내의 각각의 유니코드 문자에 대하여 유니코드의 UTF-8 바이트 위치와 유니코드 룬을 하나씩 가져올 수 있습니다.

## 3. Golang 어떤 데이터 형식을 이용하는가?

Golang:다음과 같은 형식을 사용한다.

- Method
- Boolean
- Numeric
- String
- Array
- Slice
- Struct
- Pointer
- Function
- Interface
- Map
- Channel

## 4. Golang 프로그램에서 패키지는 무엇입니까?

패키지(pkg)는 Go 소스 파일 또는 기타 패키지가 포함된 이동 작업 공간 내의 디렉터리입니다. 소스 파일의 모든 기능, 변수 및 유형은 연결된 패키지에 저장됩니다.

## 6. Goroutine이 뭐예요? 어떻게 막죠?

고루틴은 특별한 고루틴 스레드를 사용하여 다른 고루틴과 동시에 실행되는 함수 또는 메서드입니다. 고루틴 스레드는 일반 스레드보다 가볍고, 대부분의 Golang 프로그램은 수천 개의 고루틴을 한 번에 사용합니다.

signal channel에 값을 전송하여 루틴을 중지할 수 있습니다. Goroutine은 확인하라는 명령을 받은 경우에만 신호에 응답할 수 있으므로 for 루프 상단과 같은 논리적 위치에 검사를 포함해야 합니다.

## 7. 런타임에 변수 유형을 확인하는 방법은 무엇입니까?

type switch는 런타임에 변수의 유형을 확인하는 가장 좋은 방법입니다. type switch는 값이 아닌 유형별로 변수를 평가합니다. 각 스위치에는 조건문으로 작동하는 하나 이상의 케이스와 참이 없는 경우 실행되는 기본 케이스가 포함되어 있습니다.

```golang
package main

import "fmt"

func do(i interface{}) {
  switch v := i.(type) {
  case int:
    fmt.Printf("Double %v is %v\n", v, v*2)
  case string:
    fmt.Printf("%q is %v bytes long\n", v, len(v))
  default:
  fmt.Printf("I don't know  type %T!\n", v)
  }
}

func main() {
  do(21)
  do("hello")
  do(true)
}
```

## 9. Golang에서 테스트 단계를 설명합니다

Golang은 맞춤형 테스트 제품군을 통해 패키지의 자동 테스트를 지원합니다.

## 10. function closure란 무엇입니까?

function closure는 본문 외부에서 변수를 참조하는 함수 값입니다. 함수는 참조된 변수에 액세스하여 값을 할당할 수 있습니다.

## 11. Golang은 상속을 어떻게 하나요?

Goalng에는 상속이 없습니다. 왜냐하면 Golang은 클래스를 지원하지 않습니다. 상속을 한다면 자식 구조체에 부모 구조체를 embedded 형식으로 지정하여 구현할 수 있습니다.

## 12. Go 인터페이스를 설명합니다. 그것들은 무엇이고 어떻게 작동합니까?

인터페이스는 특정 값이 가지고 있기를 기대하는 메서드 집합입니다. 인터페이스는 동작을 수행할 수 있는 타입이 지녀야 하는 동작들의 집합입니다.

## 13. golang에서 Lvalue과 Rvalue 값은 무엇입니까?

Lvalue

- Refers to a memory location
- Represents a variable identifier
- Mutable
- May appear on the left or right side of the = operator

Rvalue

- Represents a data value stored in memory
- Represents a constant value
- Always appears on the = operator’s right side.

## 15. 함수에서 여러 값을 반환할 수 있습니까?

예. Go 함수는 반환문에서 각각 쉼표로 구분된 여러 값을 반환할 수 있습니다.
