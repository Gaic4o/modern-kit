# mapValues

주어진 객체의 각 값에 대해 제공된 `변환 함수`를 호출하여 새 객체를 생성하는 함수입니다. 반환된 객체는 원본 객체의 값들을 복사하여 변환한 후 생성된 새로운 객체입니다.

## Code

[🔗 실제 구현 코드 확인](https://github.com/modern-agile-team/modern-kit/blob/main/packages/utils/src/object/mapValues/index.ts)

## Benchmark

- `hz`: 초당 작업 수
- `mean`: 평균 응답 시간(ms)

|이름|hz|mean|성능|
|------|---|---|---|
|modern-kit/mapValues|7,168,899,49|0.0001|`fastest`|
|lodash/mapValues|3,676,343,30|0.0003|`slowest`|

- **modern-kit/mapValues**
  - `1.95x` faster than lodash/mapValues


## Interface

```ts title="typescript"
const mapValues: <T, R>(
  object: Record<string | number, T>,
  iteratee: (iterateData: {
    key: string | number;
    value: T;
    object: Record<string | number, T>;
  }) => R
) => Record<string | number, R>
```

## Usage

```ts title="typescript"
import { mapValues } from '@modern-kit/utils';

const users = {
  fred: { user: 'fred', age: 40 },
  pebbles: { user: 'pebbles', age: 1 }
};

const newUsers = mapValues(users, ({ value }) => value.age);
// { fred: 40, pebbles: 1 }
```