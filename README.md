# kotlin-calculator-precourse

# 문자열 덧셈 계산기

## 요구 사항

입력한 문자열에서 숫자를 추출하여 더하는 계산기를 구현합니다.

### 1. 기본 구분자(쉼표, 콜론)를 기준으로 숫자를 분리하여 합을 반환

- 입력된 문자열을 쉼표(`,`) 또는 콜론(`:`)을 기준으로 분리합니다.
- 분리된 숫자를 합산하여 결과를 반환합니다.
- 입력 예시: `"1,2:3"` → 결과: `6`
- 입력이 빈 문자열일 경우 결과는 `0`이어야 합니다.

### 2. 커스텀 구분자 지원

- 문자열 앞부분에 `"//"`와 `"\n"` 사이에 커스텀 구분자를 정의할 수 있습니다.
- 커스텀 구분자로 지정된 문자를 기준으로 숫자를 분리하고, 그 합을 반환합니다.
- 입력 예시: `"//;\n1;2;3"` → 결과: `6`

### 3. 잘못된 입력에 대한 예외 처리

- 음수나 숫자가 아닌 값이 포함된 경우 `IllegalArgumentException`을 발생시킵니다.
- 예외 발생 시 적절한 메시지를 출력하고 프로그램이 종료되지 않도록 합니다.

## 프로그램 구조

### `main()`

프로그램의 진입점입니다. 사용자의 입력을 받아 검증하고, 각 단계별로 기능을 실행하여 최종 결과를 출력합니다.

### 주요 함수 및 역할

#### 1. `checkInputIsEmpty()`

- 입력값이 빈 문자열인 경우 `IllegalArgumentException`을 발생시킵니다.

#### 2. `getSeparatedValues()`

- 입력된 문자열을 기준으로 기본 구분자 또는 커스텀 구분자를 사용하여 숫자를 분리합니다.
- 기본 구분자는 쉼표(`,`)와 콜론(`:`)이며, 커스텀 구분자가 지정된 경우 이를 사용하여 분리합니다.

#### 3. `getSeparatorState()`

- 문자열이 커스텀 구분자를 사용하는지 여부를 판단하고, 이에 맞는 구분자를 반환합니다.
- 커스텀 구분자가 존재하는 경우, 해당 구분자를 추출하여 반환합니다.

#### 4. `checkIsValidValue()`

- 각 숫자가 유효한지(숫자가 아닌 값이거나 음수인지) 확인합니다.
- 유효하지 않은 경우 `IllegalArgumentException`을 발생시킵니다.

#### 5. `getSumOfNumbers()`

- 분리된 숫자를 정수로 변환하여 합산한 결과를 반환합니다.

### 확장 함수

#### `String.isNotNumeric()`

- 문자열이 숫자가 아닌 경우 `true`를 반환합니다.

#### `String.isNegativeNumber()`

- 문자열이 음수인 경우 `true`를 반환합니다.

## 예외 처리

- 입력값이 비어 있거나 유효하지 않은 값이 포함된 경우 `IllegalArgumentException`을 발생시킵니다.
- 예외 발생 시 적절한 에러 메시지를 출력합니다.

## 메시지 상수

- `MESSAGE_FOR_GUIDE_CALCULATE`: "덧셈할 문자열을 입력해 주세요."
- `MESSAGE_INVALID_INPUT`: "잘못된 입력입니다."

## 실행 예시

```
덧셈할 문자열을 입력해 주세요. 1,2:3 

결과 : 6
```

## 참고 자료

- [프리코스 진행 가이드 문서](https://nextstep.camp)