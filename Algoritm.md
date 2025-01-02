# Algorithm
## 정렬(Sorting)
#### 기본 정렬 알고리즘
- 데이터 집합을 특정 순서(예: 오름차순 또는 내림차순)로 재배열하는 방법

##### 1. 버블 정렬(Bubble Sort)
- **정의**: 인접한 두 요소를 비교하여 정렬이 완료될 때까지 반복적으로 교환하는 정렬 알고리즘.
- **설명**: 데이터가 정렬될수록 비교와 교환이 줄어드는 단순한 알고리즘.
- **동작 방식**:
  1. 리스트의 첫 번째 요소부터 시작하여 인접한 두 요소를 비교.
  2. 두 요소의 순서가 잘못되었으면 교환.
  3. 마지막 요소까지 반복한 뒤, 다시 처음부터 과정 반복.
  4. 정렬이 완료되면 종료.
- **장점**: 구현이 간단하고 직관적.
- **단점**: 성능이 낮아 대규모 데이터 정렬에 부적합.
- **활용 예시**: 학습 목적으로 사용되며 실제 응용에서는 드물게 사용됨.

##### 2. 선택 정렬(Selection Sort)
- **정의**: 리스트에서 최소 또는 최대 값을 찾아 이를 정렬된 부분으로 옮기는 방식.
- **설명**: 매 단계마다 남은 리스트에서 가장 작은 요소를 선택하여 정렬.
- **동작 방식**:
  1. 전체 리스트에서 최소값을 찾아 첫 번째 요소와 교환.
  2. 두 번째 요소부터 나머지 리스트에서 최소값을 찾아 교환.
  3. 끝까지 반복.
- **장점**: 구현이 간단하며 교환 횟수가 적음.
- **단점**: 비교 연산이 많아 대규모 데이터에는 비효율적.
- **활용 예시**: 작은 데이터 정렬이나 메모리 공간이 제한적인 경우.

##### 3. 삽입 정렬 (Insertion Sort)
- **정의**: 데이터를 하나씩 확인하며, 이미 정렬된 리스트에 적절한 위치에 삽입하는 정렬 알고리즘.
- **설명**: 정렬된 부분과 정렬되지 않은 부분으로 나누어 진행.
- **동작 방식**:
  1. 두 번째 요소부터 시작하여, 앞의 요소들과 비교.
  2. 적절한 위치를 찾아 삽입.
  3. 모든 요소를 처리할 때까지 반복.
- **장점**: 작은 데이터나 거의 정렬된 데이터에서 매우 효율적.
- **단점**: 데이터가 많거나 무작위로 섞인 경우 비효율적.
- **활용 예시**: 실시간으로 데이터를 삽입 및 정렬해야 하는 경우(예: 카드 정렬).

#### 고급 정렬 알고리즘
- 시간 복잡도가 더 낮거나 특정 상황에서 더 효율적인 정렬 알고리즘.
- 기본 정렬 알고리즘보다 복잡하지만, 데이터의 크기가 커질수록 더 높은 성능.

##### 1. 병합 정렬 (Merge Sort)
- **정의**: 분할 정복 알고리즘을 사용하여 리스트를 반으로 나누어 정렬한 후 병합하는 방식의 정렬 알고리즘.
- **설명**: 병합 정렬은 데이터를 계속해서 두 개의 부분으로 나누고, 각 부분을 정렬하여 최종적으로 하나의 정렬된 리스트를 만듭니다. 병합 과정에서 두 개의 정렬된 리스트를 하나로 합치기 때문에 안정적인 정렬을 제공합니다.
- **동작 방식**:
  1. 리스트를 계속해서 반으로 나눈다.
  2. 나누어진 리스트들이 길이가 1이 될 때까지 재귀적으로 분할한다.
  3. 길이가 1인 리스트들이 각각 정렬된 상태로 병합되기 시작한다.
  4. 병합 과정에서 두 개의 정렬된 리스트를 비교하여 하나의 정렬된 리스트로 합친다.
  5. 최종적으로 하나의 정렬된 리스트가 완성된다.
- **장점**:
  - 안정 정렬 (같은 값의 순서가 바뀌지 않음).
  - 최악의 경우에도 시간 복잡도가 \(O(n \log n)\)로 일정하게 유지된다.
  - 매우 큰 데이터셋에서 효율적.
- **단점**:
  - 추가적인 메모리 공간이 필요하다 (병합 과정에서 임시 배열을 사용).
  - 리스트의 크기가 작을 경우 다른 알고리즘에 비해 비효율적일 수 있다.
- **활용 예시**:
  - 대규모 데이터셋을 정렬할 때 적합.
  - 데이터의 순서가 중요하고, 안정적인 정렬이 필요한 경우 (예: 데이터베이스의 레코드 정렬).

##### 2. 퀵 정렬 (Quick Sort)
- **정의**: 분할 정복 알고리즘을 이용해 리스트를 정렬하는 알고리즘으로, 피벗을 기준으로 데이터를 분할하고 정렬된 결과를 반환한다.
- **설명**: 퀵 정렬은 하나의 피벗을 선택하여 배열을 두 부분으로 나누고, 재귀적으로 이 부분들을 다시 퀵 정렬하는 방식이다. 피벗을 기준으로 왼쪽에는 피벗보다 작은 값들이, 오른쪽에는 피벗보다 큰 값들이 위치하게 되며, 이를 반복하여 최종적으로 정렬을 완료한다.
- **동작 방식**:
  1. 리스트에서 하나의 피벗을 선택한다.
  2. 피벗을 기준으로 왼쪽에는 피벗보다 작은 값, 오른쪽에는 피벗보다 큰 값을 배치한다.
  3. 왼쪽과 오른쪽 부분 리스트에 대해 재귀적으로 퀵 정렬을 적용한다.
  4. 리스트가 더 이상 나눠지지 않을 때까지 반복한다.
- **장점**:
  - 평균 시간 복잡도 \(O(n \log n)\)으로 매우 빠르다.
  - 제자리 정렬 (in-place)로 추가적인 메모리 공간을 적게 사용한다.
- **단점**:
  - 최악의 경우 시간 복잡도가 \(O(n^2)\)로 비효율적일 수 있다.
  - 피벗을 잘못 선택하면 성능이 급격히 나빠질 수 있다.
- **활용 예시**:
  - 실시간 처리 시스템에서 빠른 정렬을 요구할 때.
  - 데이터가 크고 비교 기반 정렬이 필요한 경우.

##### 3. 힙 정렬 (Heap Sort)
- **정의**: 힙 자료 구조를 이용하여 정렬을 수행하는 알고리즘으로, 힙 트리 구조를 활용하여 최대 힙 또는 최소 힙을 구성하고, 이 구조를 이용해 데이터를 정렬한다.
- **설명**: 힙 정렬은 배열을 힙 트리 구조로 변환한 후, 루트 노드(최대 값 또는 최소 값)를 배열의 끝으로 이동시키고 나머지 리스트에서 다시 힙 트리를 구성하여 반복하는 방식이다.
- **동작 방식**:
  1. 배열을 힙 구조로 만든다.
  2. 루트 노드(최대/최소 값)를 리스트의 끝으로 보낸다.
  3. 나머지 부분에 대해 힙을 다시 구성한다.
  4. 전체 리스트가 정렬될 때까지 반복한다.
- **장점**:
  - 시간 복잡도가 \(O(n \log n)\)으로 일정하게 유지된다.
  - 제자리 정렬 (in-place)로 추가적인 메모리 공간이 적게 필요하다.
- **단점**:
  - 다른 \(O(n \log n)\) 알고리즘에 비해 상수 시간에서 비효율적일 수 있다.
- **활용 예시**:
  - 실시간 시스템에서 데이터를 효율적으로 정렬해야 할 때.
  - 우선순위 큐 구현에 적합.

##### 4. 기수 정렬 (Radix Sort)
- **정의**: 숫자나 문자열을 각 자릿수를 기준으로 정렬하는 비교 기반이 아닌 정렬 알고리즘이다.
- **설명**: 기수 정렬은 LSD(Least Significant Digit) 또는 MSD(Most Significant Digit) 방식을 사용하여, 각 자릿수를 기준으로 반복적으로 정렬을 수행한다. 이를 통해 정렬을 수행하며, 주로 숫자나 문자열과 같은 범위가 한정된 데이터에 사용된다.
- **동작 방식**:
  1. 숫자의 자릿수를 기준으로 정렬을 시작한다.
  2. 각 자릿수별로 LSD 또는 MSD 방식으로 정렬을 반복한다.
  3. 자릿수를 모두 정렬한 후 최종적으로 정렬된 리스트가 완성된다.
- **장점**:
  - 비교 기반이 아닌 정렬으로 \(O(n)\) 시간 복잡도를 가질 수 있다.
  - 데이터 범위가 좁고 일정할 때 매우 효율적이다.
- **단점**:
  - 숫자의 자릿수나 데이터 범위가 크면 메모리 사용량이 증가할 수 있다.
  - 범위가 매우 크거나 실수 데이터에는 부적합하다.
- **활용 예시**:
  - 우편번호, 전화번호와 같이 고정된 범위의 정렬.
  - 대규모의 정수 데이터를 다룰 때.

##### 5. 계수 정렬 (Counting Sort)

- **정의**: 각 데이터의 빈도를 세어 정렬하는 비교 기반이 아닌 알고리즘이다. 범위가 제한된 데이터에 매우 효율적이다.
- **설명**: 계수 정렬은 각 값이 배열에 등장한 횟수를 세는 방식으로 작동하며, 각 데이터의 빈도를 기반으로 정렬된 결과를 만들어낸다. 범위가 제한된 정수 데이터에 적합하다.
- **동작 방식**:
  1. 데이터 값의 빈도를 셀 카운트 배열을 만든다.
  2. 카운트 배열에서 각 값의 등장 빈도를 기반으로 최종 위치를 결정한다.
  3. 각 값들을 정렬된 배열에 배치한다.
- **장점**:
  - 선형 시간 복잡도 \(O(n + k)\)로 매우 빠르다.
  - 비교 기반이 아니므로 속도가 매우 빠르다.
- **단점**:
  - 데이터의 범위가 매우 클 경우 비효율적이다.
  - 추가적인 메모리 공간을 많이 사용한다.
- **활용 예시**:
  - 정수 데이터의 정렬, 학점 계산 등.

##### 6. 셸 정렬 (Shell Sort)

- **정의**: 삽입 정렬의 일반화된 형태로, 데이터를 일정 간격(gap)으로 나누어 부분 리스트를 정렬한 후, 간격을 점차 줄여 가며 정렬을 수행하는 알고리즘.
- **설명**: 셸 정렬은 삽입 정렬을 개선한 알고리즘으로, 일정 간격을 두고 삽입 정렬을 수행하여 전체적으로 데이터가 정렬되도록 합니다. 이후 간격을 줄여가며 정렬을 반복한다.
- **동작 방식**:
  1. 데이터를 일정 간격으로 나누어 삽입 정렬을 수행한다.
  2. 간격을 점차 줄여가며 삽입 정렬을 반복한다.
  3. 간격이 1일 때 최종 정렬을 완료한다.
- **장점**:
  - 삽입 정렬보다 빠르며, 중간 정도 크기의 리스트에서 좋은 성능을 발휘한다.
  - 제자리 정렬 (in-place)이다.
- **단점**:
  - 최적의 간격을 찾는 것이 어렵고, 그에 따라 성능 차이가 클 수 있다.
- **활용 예시**:
  - 작은 규모의 데이터 정렬, 간단한 알고리즘을 사용할 수 있는 환경에서 유용하다.

#### 비교 기반 정렬 (Comparison-based Sort)과 비비교 정렬 (Non-comparison Sort)의 차이
  - **정의**:
  - **비교 기반 정렬**: 두 요소를 비교하여 정렬을 수행하는 알고리즘입니다. 각 데이터 간의 크기 관계를 비교하는 방식으로 정렬이 이루어집니다.
  - **비비교 정렬**: 두 요소를 비교하지 않고 다른 방식으로 정렬을 수행하는 알고리즘입니다. 보통 데이터의 특성을 이용하거나 범위에 의존하는 방식으로 동작합니다.
- **동작 방식**:
  - **비교 기반 정렬**: 
    - 요소들 간의 직접적인 비교를 통해 데이터를 정렬합니다. 예를 들어, 퀵 정렬, 병합 정렬, 힙 정렬 등이 해당됩니다.
    - 각 요소들 간의 비교를 통해 어느 것이 더 작은지, 큰지를 판단하여 정렬합니다.
  - **비비교 정렬**: 
    - 데이터의 특성을 이용하거나, 범위 정보만을 활용하여 정렬을 수행합니다. 예를 들어, 계수 정렬, 기수 정렬, 버킷 정렬 등이 해당됩니다.
    - 비교 없이 데이터의 범위나 빈도 등을 기반으로 정렬을 진행합니다.
- **시간 복잡도**:
  - **비교 기반 정렬**:
    - 최악의 경우 시간 복잡도가 \(O(n \log n)\)로 제한됩니다. 예를 들어, 퀵 정렬과 병합 정렬은 최악의 경우에도 \(O(n \log n)\)입니다.
    - 하지만, 최악의 경우 \(O(n^2)\)가 될 수 있는 알고리즘도 있습니다 (예: 선택 정렬, 버블 정렬).
  - **비비교 정렬**:
    - 특정 조건에서 시간 복잡도가 선형인 경우도 있습니다. 예를 들어, 계수 정렬과 기수 정렬은 \(O(n + k)\)로 동작할 수 있으며, \(k\)는 데이터 범위나 자릿수입니다.
    - 데이터 범위가 좁고 특정 조건이 맞을 때 매우 효율적입니다.
- **장점**:
  - **비교 기반 정렬**:
    - 범용성이 높고, 어떤 종류의 데이터에 대해서도 동작합니다.
    - 일반적으로 데이터의 특성에 의존하지 않고, 모든 종류의 데이터를 처리할 수 있습니다.
  - **비비교 정렬**:
    - 특정 조건에서 매우 빠를 수 있으며, 선형 시간 복잡도를 달성할 수 있습니다.
    - 대규모 정수 데이터나 범위가 정해진 데이터 처리에 적합합니다.
- **단점**:
  - **비교 기반 정렬**:
    - 최악의 경우 시간 복잡도가 \(O(n \log n)\)로 한정되어 있으며, 비교 연산이 많아 데이터 크기가 커질수록 시간이 많이 걸릴 수 있습니다.
  - **비비교 정렬**:
    - 데이터의 범위가 크거나 데이터의 특성이 다양할 경우 비효율적일 수 있습니다.
    - 범위가 넓거나 실수형 데이터 등에는 적합하지 않거나 성능이 떨어질 수 있습니다.
- **활용 예시**:
  - **비교 기반 정렬**:
    - 다양한 종류의 데이터에 대해 정렬이 필요한 경우. (예: 퀵 정렬, 병합 정렬, 힙 정렬 등)
  - **비비교 정렬**:
    - 특정 데이터 타입에 대해 빠른 정렬이 필요할 때. (예: 계수 정렬, 기수 정렬, 버킷 정렬 등)

## 탐색(Searching)
#### 기본 탐색 알고리즘
##### 1. 선형 탐색(Linear Search)
- **정의**: 리스트에서 원하는 값을 처음부터 끝까지 순차적으로 찾아가는 탐색 알고리즘이다.
  
- **설명**: 선형 탐색은 리스트의 모든 요소를 차례대로 비교하여 검색하는 방식이다. 리스트가 정렬되어 있지 않아도 사용 가능하며, 값이 나타날 때까지 검색을 진행한다.
  
- **동작 방식**:
  1. 첫 번째 요소부터 마지막 요소까지 원하는 값을 찾을 때까지 순차적으로 탐색한다.
  2. 값을 찾으면 탐색을 종료하고, 찾은 인덱스나 값을 반환한다.
  3. 리스트에 값이 없으면 끝까지 탐색한 후 값이 없다는 메시지를 반환한다.
  
- **시간 복잡도**:
  - 최악 시간 복잡도: \(O(n)\)
  - 최선 시간 복잡도: \(O(1)\)
  - 평균 시간 복잡도: \(O(n)\)
  
- **장점**:
  - 구현이 간단하다.
- **단점**:
  - 리스트의 크기가 커질수록 탐색 속도가 느려진다.

##### 2. 이진 탐색 (Binary Search)

- **정의**: 정렬된 리스트에서 중간값을 기준으로 값을 찾아가는 탐색 알고리즘이다.
  
- **설명**: 이진 탐색은 리스트를 반으로 나누고 중간값을 비교하여, 찾고자 하는 값이 중간값보다 작은지 큰지를 판단하여 탐색 범위를 절반으로 줄여가는 방식이다.
  
- **동작 방식**:
  1. 리스트의 중간 요소를 선택하고, 찾고자 하는 값과 비교한다.
  2. 값이 중간값보다 작으면 왼쪽 절반을, 크면 오른쪽 절반을 선택하여 탐색 범위를 좁힌다.
  3. 반복적으로 이 과정을 수행하다가 원하는 값을 찾으면 탐색을 종료한다.

- **장점**:
  - 매우 빠른 탐색 속도를 제공한다 (\(O(\log n)\)).
  - 정렬된 리스트에서 효율적으로 사용할 수 있다.
  
- **단점**:
  - 리스트가 반드시 정렬되어 있어야 한다.

#### 이진 탐색 변형(Lower/Upper bound)
- Lower Bound와 Upper Bound는 정렬된 데이터에서 특정 값을 기준으로 가장 가까운 값(또는 위치)을 찾는 문제이다.  
- 이진 탐색 트리(BST)나 배열에서 효율적으로 구현할 수 있다.

##### Lower bound
- **정의**: 찾고자 하는 값 이상인 첫 번째 값을 반환.
- **목적**: 특정 값 이상이 처음 나타나는 위치를 찾음.
- 예제
-- 배열: `[1, 3, 5, 7, 9]`
-- 찾는 값: `6`
-- Lower Bound: `7` (6 이상인 첫 번째 값)
- 동작 방식
    1. 이진 탐색을 수행.
    2. 현재 값이 찾는 값 이상이면 결과를 갱신하고, 왼쪽 부분으로 이동.
    3. 현재 값이 찾는 값보다 작으면 오른쪽 부분으로 이동.
    4. 탐색이 끝나면 Lower Bound 값이 결정됨.

##### Upper Bound
- **정의**: 정렬된 배열 또는 데이터 구조에서 찾고자 하는 값보다 큰 첫 번째 값의 위치를 반환한다.
- **목적**: 특정 값을 초과하는 값이 처음 나타나는 위치를 효율적으로 찾는다.

- 동작 방식
    1. **이진 탐색**을 기반으로 동작.
    2. 현재 값이 **찾는 값보다 작거나 같으면** 오른쪽 부분 탐색.
    3. 현재 값이 **찾는 값보다 크면** 결과를 갱신하고 왼쪽 부분 탐색.
    4. 탐색이 끝나면 Upper Bound 값이 결정됩니다.

- 시간 복잡도
-- **시간 복잡도**: \(O(\log N)\), \(N\)은 배열의 크기.
-- **공간 복잡도**: \(O(1)\) (비재귀적인 경우).

#### 고급 탐색 알고리즘
##### 이진 검색 트리(Binary Search Tree) 기반 탐색
- **정의**:  
  이진 탐색 트리는 각 노드의 왼쪽 자식이 부모 노드보다 작고, 오른쪽 자식이 부모 노드보다 큰 특성을 가진 이진 트리

- 동작 방식
    1. 루트 노드에서 시작.
    2. **찾고자 하는 값이 현재 노드보다 작으면** 왼쪽 자식으로 이동.
    3. **찾고자 하는 값이 현재 노드보다 크면** 오른쪽 자식으로 이동.
    4. 현재 노드 값이 찾는 값과 같으면 탐색 종료.
    5. 노드가 없거나 모든 경로를 탐색해도 값을 찾지 못하면 실패.

##### 해시 기반 탐색(Hash-based Search)
- **정의**:
  해시 기반 탐색은 해시 테이블(Hash Table)을 사용하여 데이터를 저장하고, 키(Key)를 기반으로 데이터를 저장하거나 검색

- 동작 방식
    1. **해시 함수(Hash Function)**:  
   -- 입력 키를 고정 크기의 해시 값으로 변환.
   -- 예: \( \text{Hash(Key)} = \text{Index} \)
    2. **저장**:  
   -- 해시 값을 계산하여 해당 인덱스에 데이터를 저장.
    3. **검색**:  
   -- 키를 해시 함수에 입력하여 인덱스를 계산한 뒤 데이터 검색.
    4. **충돌 처리**:  
   -- 동일한 해시 값을 가지는 키들이 발생하면, 이를 해결하기 위한 방법 필요.
- 충돌 처리 방법
    1. **체이닝(Chaining)**:
   -- 동일한 해시 값에서 발생한 충돌을 연결 리스트로 저장.
   -- 장점: 동적 데이터 추가에 유리.
   -- 단점: 링크를 따라가며 검색해야 하므로 최악의 경우 성능 저하.
    2. **오픈 어드레싱(Open Addressing)**:
   -- 해시 테이블 내 빈 공간을 찾아 충돌을 해결.
   -- 방법: 선형 탐사, 이차 탐사, 이중 해싱.
   -- 장점: 메모리 절약.
   -- 단점: 테이블이 꽉 차면 성능 저하.

- **활용 예시**:
  - 키-값 쌍으로 데이터를 빠르게 찾을 필요가 있을 때.
  - 중복된 데이터를 빠르게 처리하고, 검색 성능을 최적화할 때.

##### 트라이(Trie) 기반 탐색
- **정의**:  
  트라이(Trie)는 문자열을 저장하고 탐색하기 위해 설계된 트리 기반 데이터 구조.

- 동작 방식:
    1. **삽입**:  
   -- 문자열의 각 문자를 노드로 저장.
   -- 문자열의 끝을 나타내기 위해 **종료 마커**를 설정.
    2. **탐색**:  
   -- 문자열의 각 문자를 노드에서 차례대로 따라가며 존재 여부 확인.
    3. **삭제**:  
   -- 문자열의 끝부터 역순으로 노드를 삭제하며, 다른 문자열의 일부가 아닌 노드만 제거.

- **활용 예시**:
  - 노드 기반 자료구조에서, 문자열의 공통 접두사를 공유.
  - 접두사 기반 단어 가능한 단어 추천 기능

#### 탐색 알고리즘의 시간 복잡도 분석
- 탐색 알고리즘은 주어진 데이터 집합에서 특정 값을 찾는 방법을 제공하는 알고리즘이다. 각 탐색 알고리즘은 데이터의 크기와 형태에 따라 시간 복잡도가 다르다.

##### 1. **선형 탐색 (Linear Search)**
- **설명**: 선형 탐색은 리스트의 첫 번째 요소부터 마지막 요소까지 차례로 비교하며 검색하는 방법이다. 정렬 여부에 관계없이 데이터를 하나씩 비교 탐색한다.
- **시간 복잡도**:
  - **최악의 경우**: \(O(n)\) – 모든 요소를 다 확인해야 할 경우.
  - **평균의 경우**: \(O(n)\) – 목표 값이 리스트 중간에 있을 때도 모든 요소를 평균적으로 확인해야 함.
  - **최선의 경우**: \(O(1)\) – 첫 번째 요소가 목표 값일 때.
- **활용 예시**: 
  - 데이터가 정렬되지 않았거나 크기가 작을 때 유용.

##### 2. **이진 탐색 (Binary Search)**

- **설명**: 이진 탐색은 정렬된 배열에서 값을 찾는 효율적인 방법으로, 리스트를 반복적으로 절반으로 나누어 목표 값을 찾는다.
- **시간 복잡도**:
  - **최악의 경우**: \(O(\log n)\) – 리스트를 반으로 나누어가며 검색하므로 탐색할 수 있는 범위가 빠르게 줄어듦.
  - **평균의 경우**: \(O(\log n)\) – 항상 동일한 시간 복잡도를 가짐.
  - **최선의 경우**: \(O(1)\) – 첫 번째 비교에서 바로 목표 값을 찾을 수 있을 때.
- **활용 예시**: 
  - 데이터가 이미 정렬되어 있을 때, 검색 작업이 많을 때.
  - 범위가 크고, 검색의 효율성이 중요한 경우.

##### 3. **이진 탐색 트리 기반 탐색 (Binary Search Tree, BST)**

- **설명**: 이진 탐색 트리는 각 노드가 왼쪽 자식 노드보다 크고 오른쪽 자식 노드보다 작은 특성을 가진다.
- **시간 복잡도**:
  - **최악의 경우**: \(O(n)\) – 트리가 편향된 형태일 경우 (예: 일직선 형태).
  - **평균의 경우**: \(O(\log n)\) – 트리가 균형을 이루고 있을 때.
  - **최선의 경우**: \(O(\log n)\) – 트리가 균형을 이루며 목표 값이 중간에 있을 때.
- **활용 예시**:
  - 동적 데이터 집합에서 빠른 검색, 삽입, 삭제가 필요할 때.

##### 4. **해시 기반 탐색 (Hash-based Search)**

- **설명**: 해시 탐색은 해시 테이블을 이용하여 키-값 쌍을 저장하고, 해시 함수에 의해 인덱스를 계산하여 데이터를 찾는 방법이다.
- **시간 복잡도**:
  - **최악의 경우**: \(O(n)\) – 해시 충돌이 많이 발생할 경우 모든 항목을 탐색해야 할 수도 있다.
  - **평균의 경우**: \(O(1)\) – 해시 함수가 잘 분배되어 있을 경우 매우 빠르게 검색 가능.
  - **최선의 경우**: \(O(1)\) – 해시 값이 바로 원하는 항목으로 나오는 경우.

- **활용 예시**:
  - 키-값 쌍으로 데이터를 빠르게 찾을 필요가 있을 때.
  - 중복된 데이터를 빠르게 처리하고, 검색 성능을 최적화할 때.

##### 5. **Lower/Upper bound**

##### 6. **트라이(Trie) 기반 탐색**

##### 결론

- **선형 탐색**은 데이터가 정렬되지 않았거나 작은 크기일 때 유용하며, 간단하지만 시간 복잡도가 커질 수 있습니다.
- **이진 탐색**은 정렬된 배열에서 빠른 검색을 제공하며, \(O(\log n)\)의 효율성을 가집니다.
- **해시 탐색**은 해시 테이블을 이용하여 평균적으로 매우 빠른 검색 성능을 보입니다.
- **이진 탐색 트리**는 동적 데이터에 대해 효율적인 검색, 삽입, 삭제를 제공하지만 트리의 균형 상태에 따라 성능이 달라질 수 있습니다.


## 재귀 및 분할 정복

#### 재귀
- **정의**: 문제를 더 작은 동일한 형태의 하위 문제로 나누어 해결하는 방법.
  - 그 후, 각 단계에서 계산된 값을 결합하여 최종 결과를 도출한다.
- **기본 재귀(Recursive case)**:
  - 문제를 더 작은 동일한 문제로 나누는 부분이다.
  - 매 호출마다 기저 조건에 가까워짐.
- **기저 조건(Base Case)**:
  - 재귀가 멈추는 조건으로, 더 이상 재귀 호출이 필요 없는 가장 단순한 경우이다.
- **동작 방식**:
  - sample?

#### 분할 정복(Divide and Conquer)
- **정의**: 분할 정복은 문제를 더 작은 하위 문제로 나누고, 각 하위 문제를 해결한 후 결과를 합쳐서 최종 해결책을 찾는 알고리즘 설계 기법. 일반적으로 재귀를 사용하여 구현

- **동작 방식**:
  1. **분할(Divide)**: 문제를 두 개 이상의 작은 부분 문제로 나눕니다.
  2. **정복(Conquer)**: 각 부분 문제를 재귀적으로 해결합니다. (부분 문제를 더 이상 나눌 수 없는 상태까지)
  3. **결합(Combine)**: 부분 문제의 해결책을 합쳐서 전체 문제의 해결책을 만듭니다.

- **시간 복잡도**:
  -  시간 복잡도는 보통 **마스터 정리(Master Theorem)**를 통해 계산할 수 있습니다.
  - 예를 들어, \(T(n) = aT(n/b) + O(n^d)\)와 같은 형태의 시간 복잡도를 가집니다.

- **장점**:
  - 문제를 효율적으로 분할하여 더 작은 문제로 해결함으로써 복잡한 문제를 쉽게 해결할 수 있습니다.
  - 분할 정복 기법을 사용한 알고리즘은 일반적으로 시간이 효율적이고, 큰 문제를 작은 문제로 나누어 해결할 수 있습니다.

- **단점**:
  - 분할과 결합의 과정에서 추가적인 공간을 사용할 수 있습니다.
  - 일부 문제에서 비효율적일 수 있으며, 하위 문제들이 독립적이지 않으면 더 복잡한 처리가 필요할 수 있습니다.

#### 재귀와 분할 정복의 차이점

| **항목**              | **재귀 (Recursion)**                               | **분할 정복 (Divide and Conquer)**                         |
|---------------------|--------------------------------------------------|-------------------------------------------------------|
| **정의**              | 문제를 작은 부분 문제로 나누어 해결하는 방식.       | 문제를 분할하여 해결하고, 그 결과를 합쳐 최종 해결책을 찾는 방식.  |
| **주요 요소**          | 기저 사례(Base Case), 재귀 호출(Recursive Case)      | 분할(Divide), 정복(Conquer), 결합(Combine)               |
| **구현 방식**          | 주로 함수 내부에서 자기 자신을 호출하여 처리함.      | 재귀적으로 문제를 분할하고, 각 하위 문제를 해결하여 결합.   |
| **시간 복잡도 분석**    | 재귀 함수의 호출 횟수에 따라 시간 복잡도를 분석함.   | 재귀적 분할과 결합의 시간 복잡도 분석 (보통 마스터 정리로 분석). |
| **예시**              | 팩토리얼 계산, 피보나치 수열 계산, 하노이의 탑.      | 병합 정렬(Merge Sort), 퀵 정렬(Quick Sort), 이진 탐색(Binary Search). |

#### 백트래킹 (Backtracking)

- **정의**: 백트래킹은 가능한 모든 해를 탐색하면서 유효하지 않은 해를 미리 차단하고, 유효하지 않으면 되돌아가서 다른 경로를 탐색하는 알고리즘.

- **설명**: 백트래킹은 가능한 해를 찾기 위해 선택지를 하나씩 시도하면서, 선택한 값이 문제의 조건을 만족하지 않으면 되돌아가서 다른 선택지를 시도하는 방식. 이 방식은 재귀적으로 구현되는 경우가 많으며, 주로 깊이 우선 탐색(DFS) 기법을 사용하여 해결.

- **동작 방식**:
  1. 주어진 문제에서 가능한 선택을 순차적으로 탐색한다.
  2. 선택한 값이 조건을 만족하는지 확인하고, 만족하지 않으면 바로 이전 단계로 되돌아가서 다른 값을 시도한다.
  3. 만족할 경우 다음 단계로 진행하고, 조건을 만족하는 해를 찾으면 종료한다.
  4. 모든 가능한 해를 탐색하는 방식으로 동작한다.

- **장점**:
  - 가능한 모든 해를 찾아야 할 때 유용하다.
  - 해를 찾을 때까지 계속해서 탐색하며, 특정 조건을 만족하는 해를 찾는 데 적합하다.

- **단점**:
  - 최악의 경우 모든 가능한 경로를 탐색해야 하므로 시간 복잡도가 커질 수 있다.
  - 해를 찾을 수 있는 경우가 많지 않거나, 문제가 매우 복잡하면 비효율적일 수 있다.

##### N-Queens
- **정의**:  
  N-Queens 문제는 N x N 체스판에 N개의 퀸을 놓는 문제다. 각 퀸은 다른 퀸들과 같은 행, 열, 대각선에 놓일 수 없다.
- **목표**:  
  가능한 모든 퀸 배치를 찾아 출력하거나, 하나의 해결책을 찾는 것이 목표다.
- **알고리즘**:  
  백트래킹(Backtracking) 알고리즘을 사용하여 가능한 위치를 하나씩 시도하며 해결책을 찾는다.

##### Sudoku Solver
- **정의**:  
  스도쿠는 9x9 격자에서 각 셀에 1부터 9까지의 숫자를 채우는 퍼즐이다.
- **목표**:  
  주어진 초기 상태에서 빈 칸을 채우고, 유효한 스도쿠 풀이를 찾는 것이 목표이다.
- **알고리즘**:
  백트래킹(Backtracking) 알고리즘을 사용하여 가능한 숫자를 하나씩 시도한다.


## 그리디 알고리즘(Greedy Algorithm)
- **정의**: 그리디 알고리즘은 문제를 해결하는 과정에서, 현재 상황에서 가장 좋은 선택을 반복적으로 하는 방식으로 문제를 해결하는 알고리즘.

- **설명**: 그리디 알고리즘은 전체 문제를 해결하기 전에 부분 문제를 해결하는 과정에서 각 단계에서 최선의 선택을 합니다. 이러한 선택이 최종적으로 전체 문제의 최적해로 이어지리라고 믿고 진행합니다. 그리디 알고리즘은 종종 해가 존재하는 문제에서 매우 효율적으로 동작합니다.

- **동작 방식**:
  1. 문제를 해결하는 데 필요한 여러 단계를 결정한다.
  2. 각 단계에서 현재 상태에서 가장 최선의 선택을 한다.
  3. 모든 단계가 끝날 때까지 이 과정을 반복한다.
  4. 최종적인 해결책을 구한다.

- **특징**:
  1. **탐욕적 선택 속성 (Greedy Choice Property)**: 그리디 알고리즘은 각 단계에서 가장 최선의 선택을 하여 문제를 해결한다고 가정합니다. 각 선택이 최적해로 이어진다고 믿고 선택합니다.
  2. **최적 부분 구조 (Optimal Substructure)**: 그리디 알고리즘이 최적해를 구할 수 있는 이유는 부분 문제의 최적해들이 모여서 전체 문제의 최적해를 구성하기 때문입니다.
  3. **국소 최적 해를 선택 (Local Optimal Solution)**: 그리디 알고리즘은 전체 최적해를 구하기 위해 각 단계에서 국소적으로 최적인 해를 선택합니다.
  4. **단계별 결정**: 문제를 해결하는 과정에서 각 단계에서 이전의 선택을 고려하지 않고, 그 순간에 최선의 선택을 합니다.

- **장점**:
  1. **단순하고 빠르다**: 그리디 알고리즘은 각 단계에서 최적의 선택만을 고려하므로 구현이 간단하고, 일반적으로 빠른 시간 내에 해결할 수 있습니다.
  2. **효율적인 시간 복잡도**: 그리디 알고리즘은 최적해를 찾기 위해 불필요한 계산을 하지 않으며, 대부분의 경우 시간 복잡도가 낮습니다.

- **단점**:
  1. **최적해를 보장하지 않을 수 있다**: 그리디 알고리즘은 각 단계에서 최적의 선택을 하기 때문에, 경우에 따라 전체적인 최적해를 구할 수 없습니다. 문제에 따라 최적의 해를 찾지 못할 수 있습니다.
  2. **문제 조건에 따라 비효율적일 수 있다**: 그리디 알고리즘이 항상 최적해를 보장하지 않기 때문에, 일부 문제에서는 동작하지 않거나 잘못된 결과를 도출할 수 있습니다.

- **활용 예시**:
  1. **동전 문제**: 주어진 동전의 종류로 특정 금액을 만들 때, 가장 적은 개수의 동전으로 금액을 만드는 문제.
  2. **활동 선택 문제**: 여러 개의 활동 중, 서로 겹치지 않게 최대한 많은 활동을 선택하는 문제.
  3. **크루스칼 알고리즘 (최소 스패닝 트리)**: 그래프에서 최소 비용으로 모든 정점을 연결하는 트리를 만드는 문제.
  4. **프림 알고리즘**: 프림 알고리즘은 **정점 중심의 접근법**을 사용하여 최소 신장 트리를 찾는 문제.

- **시간 복잡도**:
  - 그리디 알고리즘의 시간 복잡도는 문제의 특성에 따라 다르지만, 각 단계에서 최적 선택을 하는 방식으로 동작하므로 보통 **선택할 수 있는 항목의 수에 비례하는 시간 복잡도**를 가집니다. 예를 들어, 동전 문제에서는 동전 종류의 수만큼 비교가 이루어지며, 그리디 알고리즘은 대체로 **O(n log n)** 또는 **O(n)**의 시간 복잡도를 가질 수 있습니다.

## 동적 계획법
- **정의**: 동적 계획법은 복잡한 문제를 해결하기 위해 문제를 작은 하위 문제로 나누어, 그 하위 문제의 결과를 저장하여 반복 계산을 방지하고 효율적으로 문제를 해결하는 알고리즘 기법입니다. 주로 최적화 문제에서 사용됩니다.

- **설명**: 동적 계획법은 동일한 하위 문제가 여러 번 반복될 때, 그 결과를 저장하여 계산을 한 번만 수행하게 함으로써 효율성을 높입니다. 이를 **메모이제이션(Memoization)** 또는 **테이블화(Tabulation)** 방식으로 저장할 수 있습니다. 동적 계획법은 재귀적 접근을 통해 문제를 해결하지만, 하위 문제의 결과를 기록하여 반복 계산을 피합니다.

- **동작 방식**:
  1. 문제를 하위 문제로 나눈다.
  2. 하위 문제를 해결하면서 그 결과를 저장한다.
  3. 저장된 결과를 이용해 전체 문제를 해결한다.

- **특징**:
  1. **최적 부분 구조 (Optimal Substructure)**: 큰 문제를 해결하는 데 작은 문제들의 최적해가 결합되어야 한다는 성질입니다. 즉, 문제를 작은 하위 문제로 나눠 해결할 수 있어야 합니다.
  2. **중복되는 부분 문제 (Overlapping Subproblems)**: 동일한 하위 문제가 여러 번 발생하는 성질입니다. 동적 계획법은 이를 해결하기 위해 중간 결과를 저장합니다.

- **장점**:
  1. **시간 복잡도를 줄일 수 있다**: 중복된 계산을 피하기 위해 이미 계산된 결과를 저장하여 다시 계산하지 않으므로 효율적으로 문제를 해결할 수 있습니다.
  2. **최적해를 찾을 수 있다**: 동적 계획법은 최적화 문제에서 최적의 해결책을 보장합니다.
  
- **단점**:
  1. **공간 복잡도**: 중간 결과를 저장해야 하므로 메모리 사용량이 증가할 수 있습니다.
  2. **문제의 특징이 맞지 않으면 효과적이지 않다**: 동적 계획법은 최적 부분 구조와 중복된 부분 문제의 특성을 가진 문제에서만 효율적으로 동작합니다.

- **활용 예시**:
  1. **피보나치 수열 (Fibonacci Sequence)**: 재귀적인 방법으로 피보나치 수열을 구할 때, 같은 값을 여러 번 계산하는 중복을 방지하고 효율적으로 계산할 수 있습니다.
  2. **최대 부분 합 문제 (Maximum Subarray Problem)**: 배열에서 합이 가장 큰 부분 배열을 찾는 문제.
  3. **배낭 문제 (Knapsack Problem)**: 주어진 무게 제한 내에서 최대 가치를 얻을 수 있는 아이템을 선택하는 문제.
  4. **편집 거리 문제 (Edit Distance)**: 두 문자열 간의 최소 편집 거리를 구하는 문제.
  5. **최단 경로 문제 (Shortest Path Problem)**: 다익스트라 알고리즘처럼 그래프에서 최단 경로를 구하는 문제.

#### 메모이제이션과 타블레이션
##### 메모이제이션(Memoization)
- 정의: 중복되는 계산을 피하기 위해 이전 계산 결과를 저장하고, 필요 시 이를 재사용하는 최적화 기법
- 특징:
  - 탑다운(Top-Down) 접근법으로, 문제를 쪼개어 해결하며 하위 문제의 결과를 저장
  - 캐싱을 통해 성능을 개선하며, 메모리를 추가로 사용한다.
  - 구현이 간단하며, 재귀 호출로 문제를 자연스럽게 표현
- 장점:
  - 중복 계산을 제거하여 성능을 크게 향상시킨다.
- 단점:
  - 메모리 사용량이 증가한다.
- 예시:
  - 피보나치 수열 계산 
  - 그래프 알고리즘

##### 타뷸레이션(Tabulation)
- 정의: 문제를 부분 문제로 나눈 다음 작은 문제부터 차례대로 그 결과를 테이블에 저장하는 방식
- 특징:
  - 바텀업(Bottom-Up)으로 접근하는 방법.
  - 필요한 값들으르 미리 계산해두는 것.
  - 반복문 사용으로 구현.
- 장점:
  - 중복 계산을 제거하여 성능을 크게 향상시킨다.
- 단점:
  - 메모리 사용량이 증가한다.
- 예시:
  - 피보나치 수열 계산
  - 그래프 알고리즘

## 분할 정복 (Divide and Conquer)

- **정의**: 분할 정복은 문제를 작은 하위 문제로 나누고, 각 하위 문제를 해결한 다음, 그 결과를 결합하여 원래 문제를 해결하는 알고리즘 설계 기법입니다.

##### 동작 방식

1. **분할 (Divide)**: 문제를 더 작은 하위 문제로 나눕니다.
2. **정복 (Conquer)**: 각 하위 문제를 재귀적으로 해결합니다.
3. **결합 (Combine)**: 하위 문제의 결과를 결합하여 전체 문제의 해를 구합니다.

##### 특징

1. **재귀적 구조**: 대부분의 분할 정복 알고리즘은 재귀적으로 구현됩니다.
2. **최적 부분 구조**: 하위 문제의 최적해가 상위 문제의 해결에 기여해야 합니다.
3. **병렬 처리 가능성**: 서로 독립적인 하위 문제를 병렬로 처리할 수 있습니다.

##### 장점

1. **문제의 크기를 줄여 해결**: 대규모 문제를 해결하기 적합합니다.
2. **효율성**: 일부 문제에서는 시간 복잡도가 크게 줄어듭니다.
3. **병렬 처리 가능**: 독립적인 하위 문제로 나누어 병렬로 실행할 수 있습니다.

##### 단점

1. **재귀 호출 오버헤드**: 재귀 호출이 많아지면 오버헤드가 발생할 수 있습니다.
2. **결합 단계의 비용**: 하위 문제의 결과를 결합하는 데 추가적인 비용이 들 수 있습니다.
3. **적용 제한**: 분할이 자연스럽지 않거나 결합이 어렵다면 효율적으로 동작하지 않습니다.

## 그래프 알고리즘
- **정의**: 그래프 구조를 탐색하거나 분석하기 위한 알고리즘 집합으로, 그래프의 정점(Vertex)과 간선(Edge) 간의 관계를 효율적으로 처리합니다.
- **활용 예시**: 
1. 네비게이션 시스템
- **사용 알고리즘**: 최단 경로 알고리즘 (다익스트라, A*, 벨만-포드).
- **설명**: 도시 간 최단 경로를 계산하여 가장 빠른 길을 안내.
- **예시**: 구글 지도, 카카오맵.

2. 네트워크 설계 및 분석
- **사용 알고리즘**: 최소 신장 트리 (크루스칼, 프림 알고리즘), 플로이드-워셜.
- **설명**: 네트워크 연결 비용을 최소화하거나 최적의 라우팅 경로를 계산.
- **예시**: 인터넷 백본 네트워크 설계, 전력망 설계.

3. 소셜 네트워크 분석
- **사용 알고리즘**: BFS, DFS, 클러스터링 알고리즘.
- **설명**: 네트워크에서 사람 간 연결, 중심성 분석, 커뮤니티 탐색.
- **예시**: 페이스북 친구 추천, 링크드인 네트워크 제안.

#### 탐색 알고리즘

##### 깊이 우선 탐색(DFS, Depth-First Search)
- 정의:
  - 루트 노드에서 시작해서, 자식의 노드들을 순서대로 탐색하는 방법.
- 특징:
  - 스택을 사용하여 구현하거나 재귀 호출을 통해 구현
  - 경로가 존재하면 해당 경로를 따라 끝까지 탐색하고, 갈 곳이 없으면 뒤로 돌아가며 다른 경로 탐색.

- 동작 방식:
![image](/image/dfs-example.png) 
    1. 0 노드를 방문한다. -> 큐에 0 노드 삽입, 이후 a와 인접한 모두 노드 방문
    2. 큐에서 꺼낸 노드와 인접한 노드 모두 방문한다 -> 1, 2, 4 노드 방문
    3. 이후 1과 인접한 0,2 노드, 2와 인접한 1,3,4 노드, 4와 인접한 0, 3, 2 노드 방문
    4. 방문한 노드는 재방문 하지 않으므로 방문 순서는 0,1,2,4,3이 된다.
- 장점:
  - 구현이 간단하다.
  - 찾아야 하는 노드가 깊은 단계에 있을 수록, 그 노드가 좌측에 있을 수록 BFS보다 유리하다.
- 단점:
  - 답이 아닌 경로가 매우 깊을 때, 시간이 오래 걸릴 수 있다.
- 예시:
  - 전자 회로에서 특정 단자끼리 연결되어 있는 지

##### 너비 우선 탐색(BFS, Breadth-First Search)
- 정의:
  - 한 정점에서 시작하여 인접한 정점들을 먼저 방문한 후, 정점들의 인접 정점들을 탐색하는 방법.
- 특징:
  - 재귀적으로 동작하지 않는다.
  - 어떤 노드를 방문했는 지 여부를 반드시 검사해야 한다.

- 동작 방식:
![image](/image/bfs-example.png) 
    1. 0 노드를 방문한다. -> 큐에 0 노드 삽입, 이후 a와 인접한 모두 노드 방문
    2. 큐에서 꺼낸 노드와 인접한 노드 모두 방문한다 -> 1, 2, 4 노드 방문
    3. 이후 1과 인접한 0,2 노드, 2와 인접한 1,3,4 노드, 4와 인접한 0, 3, 2 노드 방문
    4. 방문한 노드는 재방문 하지 않으므로 방문 순서는 0,1,2,4,3이 된다.
- 장점:
  - 너비를 우선으로 탐색하므로, 답이 여러 개여도 최단 경로임을 보장
  - 최단 경로를 반드시 찾을 수 있음
- 단점:
  - 노드의 수가 많을 수록, 큐에 많은 공간이 필요함
  - 노드의 수가 많아지면, 탐색해야 하는 노드의 수가 많아져 비효율적임.
- 예시:
  - 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때
#### 최단 경로 알고리즘
- 정의:
  - 두 노드 사이의 가장 짧은 경로를 찾는 알고리즘
- 특징:
  - 간선에 가중치가 부여된다.
##### 다익스트라 알고리즘 (Dijkstra's Algorithm)
- 정의:
  - 가중치가 있는 그래프에서 시작 정점부터 다른 모든 정점까지의 최단 경로를 찾는 알고리즘.
- 특징:
  - 단일 시작점에서 다른 모든 노드까지의 최단 경로를 찾음.
  - 간선의 가중치는 음수를 허용하지 않음
  - 실시간 최단 경로 탐색 상황에 적합하다.
- 동작 방식:
    1. 출발 노드를 설정한다.
    2. 최단 거리 테이블을 초기화 한다.
    3. 방문하지 않은 노드 중 가장 짧은 노드를 선택한다.
    4. 해당 노드를 거쳐 이동하는 비용 게산하여 테이블 갱신.
- 장점:
  - 구현이 단순하다.
  - 효율적인 경로 탐색이 가능.
- 단점:
  - 모든 가중치가 양수일 때만 작동한다.
  - 대규모 네트워크에서는 계산 시간이 길어짐.
- 예시:
  - GPS 네비게이션 시스템의 최적 경로 제공
  - 물류 시스템의 화물 운송 최적의 경로 제공

##### 벨만-포드 알고리즘 (Bellman-Ford Algorithm)
- 정의:
  - 다익스트라와 유사하지만, 음수 가중치가 있을 경우에도 사용할 수 있는 알고리즘.
- 특징:
  - 단일 출발점 최단 경로 문제를 해결
  - 브루트 포스 전략을 사용한다.
- 동작 방식:
![image](/image/bellman.png) 
    1. 출발 노드 설정
    2. 최단 거리 테이블을 초기화
    3. 모든 간선에 대해 각 간선을 거쳐 다른 노드로 가는 비용을 계산하여, 테이블을 갱신 -> N-1 번 반복
- 장점:
  - 음수 가중치에서도 사용 가능하다.
- 단점:
  - 다익스트라 알고리즘에 비해 느리다.
- 예시:
  - 환율 차익 거래 방지 시스템
  - 다양한 비용 구조를 가지는 로봇의 경로 최적화

##### 플로이드-워셜 알고리즘 (Floyd-Warshall Algorithm)
- 정의:
  - 그래프에서 모든 노드 간의 최단 경로를 구하는 알고리즘
- 특징:
  - 모든 노드에서 다른 모든 노드까지의 최단 경로 계산
  - 음의 가중치가 있는 간선에서도 사용 가능
  - 2차원 배열을 사용해 최단 거리 정보 저장
- 동작 방식:
    1. 모든 노드 쌍에 대해 직접 연결된 경로의 거리를 2차원 배열에 저장.
    2. 각 노드를 중간 경유지로 고려하여 경로 갱신
    3. D[S][E] = Math.min(D[S][E], D[S][K] + D[K][E])의 점화식으로 경로 계산.
    D[S][E]는 노드 S에서 노드 E까지의 최단 거리를 저장하는 배열이다.
- 장점:
  - 모든 노드 쌍 간의 최단 경로를 한 번에 계산할 수 있다.
  - 구현이 간단함.
- 단점:
  - 시간 복잡도가 높아 대규모 그래프에서는 비효율적임.
- 예시:
  - 도시 간 최단 경로 계산
  - 항공사의 최적 비행 경로 설계

#### 최소 신장 트리
- 정의:
  - 가중치가 있는 연결 그래프에서 모든 정점을 연결하는 간선들의 합이 최소가 되는 트리를 찾는 알고리즘.
- 특징:
  - n개의 정점을 가진 그래프는 n-1개의 간선을 가진다.
  - 하나의 그래프에 여러 개의 최소 신장 트리가 존재한다.
  - 양방향 가중 그래프에서 정의된다.
  - 사이클이 생기지 않는다.

##### 크루스칼 알고리즘
- 정의:
  - 간선의 가중치가 작은 순으로 간선을 추가해 가며 최소 신장 트리를 찾는 알고리즘.
- 특징:

- 동작 방식:
    1. 그래프의 모든 간선을 가중치 기준으로 오름차순 정렬한다.
    2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선을 선택한다.
    3. 선택된 간선을 현재의 MST 집합에 추가한다.
    4. 모든 정점이 연결될 때까지 2~3 과정을 반복한다.

- 장점:
  - 구현이 간단함.
  - 메모리 사용이 효율적임.
- 단점:
  - 간선이 많은 밀집 그래프에서는 정렬에 시간이 오래 걸림.
- 예시:
  - 네트워크 설계
##### 프림 알고리즘
- 정의:
  - 시작 정점에서부터 트리를 확장해 가면서 최소 신장 트리를 찾는 알고리즘
- 특징:
  - 정점을 중심으로 MST를 만들어 나간다.
- 동작 방식:
    1. 임의의 간선을 하나 선택한다.
    2. 선택한 간선의 정점과 인접한 정점 중에서, 최소 가중치의 간선으로 연결된 정점과 연결 
    3. 모든 정점이 선택되면 완료.
- 장점:
  - 간선이 많은 그래프에서 효율적이다.
  - 시작 정점을 선택할 수 있어, MST 구성에 유리하다.
- 단점:
  - 우선순위 큐를 사용하므로, 구현이 복잡핟.
- 예시:
  - 대규모 네트워크 라우팅

#### 네트워크 플로우
- **정의**: 그래프에서 유량(Network Flow)을 계산하는 알고리즘으로, 간선의 용량(Capacity)과 흐름(Flow)을 고려하여 최대 유량 또는 최적 경로를 구합니다.

##### 에드몬드-카프 알고리즘 (Edmonds-Karp Algorithm)
- **정의**: 포드-풀커슨 알고리즘(Ford-Fulkerson)의 구현 중 하나로, BFS를 사용하여 증가 경로(Augmenting Path)를 찾습니다.

##### 푸시-재명칭 알고리즘 (Push-relabel Algorithm)
- **정의**: 유량 네트워크에서 정점을 높이(Elevation)와 초과 유량(Excess Flow)을 기반으로 유량을 조정하여 최대 유량을 계산하는 알고리즘.
- **특징**: 간선이 아니라 정점을 중심으로 동작하며, 유량의 지역적 균형을 유지하면서 최적의 흐름을 찾아갑니다.
- **시간 복잡도**: \(O(V^2E)\), \(V\): 정점 수, \(E\): 간선 수.

##### 동작 방식

###### 주요 개념

1. **높이 (Height)**:
   - 각 정점에 대해 높이를 정의하며, 높이는 소스에서 시작하여 증가.
   - 높이가 높아질수록 유량이 더 이상 이동할 수 없는 정점이 됨.

2. **초과 유량 (Excess Flow)**:
   - 정점으로 들어온 유량과 나간 유량의 차이. 초과 유량이 0이 아니면 처리가 필요.

3. **잔여 용량 (Residual Capacity)**:
   - 간선이 현재 추가로 수용할 수 있는 유량.  

###### 알고리즘 단계

1. **초기화**:
   - 소스 정점의 높이를 그래프 정점 수(\(V\))로 설정.
   - 소스에서 인접 정점으로 가능한 최대 유량을 푸시.

2. **푸시 (Push)**:
   - 초과 유량이 존재하고 잔여 용량이 남아 있는 간선으로 유량을 전송.
   - 유량은 잔여 용량과 초과 유량 중 최소값을 전송.

3. **재명칭 (Relabel)**:
   - 더 이상 푸시할 수 없는 경우, 정점의 높이를 증가.
   - 높이는 인접 간선의 높이보다 최소 1만큼 크게 설정.

4. **반복**:
   - 초과 유량이 있는 정점들에 대해 푸시와 재명칭을 반복.
   - 모든 초과 유량이 소스 또는 싱크로 전송되면 종료.

#### 위상 정렬

## 문자열 알고리즘
- 문자열을 처리하는 알고리즘

#### 문자열 검색

##### KMP 알고리즘 (Knuth-Morris-Pratt Algorithm)
- 정의: 패턴 내에서 일치하지 않는 문자가 발견되었을 때, 패턴을 이동시켜 다시 비교를 시작하는 방식으로 동작하는 알고리즘
- 특징:
  - 접두사와 접미사의 개념을 활용하여 반복되는 연산을 최소화함.
  - PI 배열이란 0~i까지의 부분 문자열에서 prefix == suffix가 될 수 있는 부분 문자열 중 가장 긴 것의 길이이다. 
- 동작 방식:
    1. PI 배열의 값을 계산한다. ex) AAAB -> {0, 1, 2, 0}
    2. 0번째부터 문자열을 비교할 때, x번째 인덱스에서 불일치 발생 시, PI배열의 x-1 값을 확인해서 그 값의 인덱스로 이동.
- 코드
  ```java
  import java.io.BufferedReader;
  import java.io.IOException;
  import java.io.InputStreamReader;

  public class Main {
    static int[] F;

    public static void main(String[] args) throws IOException {
      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
      StringBuilder sb = new StringBuilder();

      String T = br.readLine();
      String P = br.readLine();

      failureFunction(P);
      System.out.println(KMP(T, P));
      br.close();
    }

    static int KMP(String text, String pattern) {
      for (int i = 0, j = 0; i < text.length(); i++) {
        while (j > 0 && text.charAt(i) != pattern.charAt(j)) {
          j = F[j - 1];
        }

        if (text.charAt(i) == pattern.charAt(j)) {
          if (j == pattern.length() - 1) {
            return i - j;
          } else {
            ++j;
          }
        }
      }
      return -1;
    }

    static void failureFunction(String pattern) {
      F = new int[pattern.length()];

      for (int i = 1, j = 0; i < pattern.length(); i++) {
        while (j > 0 && pattern.charAt(i) != pattern.charAt(j)) {
          j = F[j - 1];
        }

        if (pattern.charAt(i) == pattern.charAt(j)) {
          F[i] = ++j;
        }
      }

    }

  }
  ```
   
- 장점:
  - 중복 비교를 방지하여 검색 속도가 빠르다.
  - 다양한 문자열 검색 문제에 적용할 수 있다.
- 단점:
  - PI 배열을 생성하여 전처리 과정이 필요하다.
  - PI 배열 생성 로직이 복잡하다.
- 예시:
  - 도시 간 최단 경로 계산
  - 텍스트 편집기나 검색 엔진에서 특정 문자열 찾기(Ctrl + F)

##### 라빈-카프 알고리즘 (Rabin-Karp Algorithm)
- 정의: 해시 함수를 이용하여 텍스트에서 특정 패턴의 위치를 찾는 방식
- 특징:
  - 접두사와 접미사의 개념을 활용하여 반복되는 연산을 최소화함.
  - 해시값은 각 문자의 아스키코드 값에 2의 제곱 수를 곱하여 더한 값.
- 동작 방식:
    1. 찾으려는 문자열의 해시 값을 계산
    2. 찾으려는 문자열의 길이만큼 첫 번째부터 긴 문자열의 해시값을 계산 후 비교
    3. 해시 값이 일치할 때 까지 인덱스를 증가하며 비교
   
- 장점:
  - 문자열을 직접 비교하지 않고 해시값을 비교하여 성능을 높인다.
  - 여러 패턴의 해시값을 한꺼번에 계산해 비교할 수 있다.
  - 해시 함수 설계에 따라 다양한 형태의 문자열 검색 문제에 적용 가능하다.
- 단점:
  - 서로 다른 문자열이 동일한 해시값을 가질 가능성이 있어 실제 문자열 비교가 추가적으로 필요하다.
  - 적절한 해시 함수를 설계하지 않으면 성능이 저하될 수 있다.
- 예시:
  - 긴 문서에서 특정 키워드나 패턴을 빠르게 검색
  - 문자열 기반 데이터에서 효율적인 검색을 수행

#### 접미사 배열 및 트라이

##### 접미사 배열 (Suffix Array)
- 정의: 문자열 형태의 데이터가 갖는 모든 접미사를 사전 순 정렬한 것
- 특징:
  - 
- 동작 방식:
![image](/image/sfxarray.jpeg) 
https://todaycode.tistory.com/103
    1. 특정 문자열의 모든 부분 문자열 생성
    2. 부분 문자열을 사전 순으로 정렬
   
- 장점:
  - 단순한 문자열 검색에 유리
- 단점:
  - 단순 구현 시 배열의 높은 계산 비용
- 예시:
  - 문자열 일치 검색

##### 접미사 트리 (Suffix Tree)
- 정의: 접미사 트라이(Suffix Trie)를 압축한 것으로, 모든 접미사를 포함한 것이다.
- 특징:
  - 패턴이 문자열에 존재하는 지 찾기 위해 사용
- 동작 방식:
    1. 문자열의 모든 접미사를 계산한다. 마지막 문자는 "$"로 항상 추가한다.
    2. 루트 노드에서 시작하여 접미사를 추가하여 트리 구조를 생성한다.
    3. 트리 구조로, 각 모든 접미사가 리프노드에 도달하게 완성한다.

    ![image](/image/sfxtree.jpeg)    
     "abac"에 대응하는 접미사
     [link](https://juggernaut.tistory.com/entry/%EC%A0%91%EB%AF%B8%EC%82%AC-%ED%8A%B8%EB%9D%BC%EC%9D%B4Suffix-Trie)
- 장점:
  - 가장 긴 반복 문자열(LRS), 가장 긴 공통 부분 문자열(LCS) 등 연산 가능
- 단점:
  - 구현이 복잡하다.
- 예시:
  - 문자열 검색
#### 롤링 해시 및 Z-알고리즘
##### 롤링 해시
- 정의: 문자열의 해시 값을 효율적으로 계산하기 위해 사용하는 기법으로, 고정된 크기의 윈도우가 문자열을 이동할 때 새로 추가된 문자와 제거된 문자를 이용해 해시 값을 빠르게 갱신하는 방식
- 특징:
  - 이전의 해시 값을 업데이트하여 시간을 줄임
  - 고정 크기의 부분 문자열 분석에 적합
- 동작 방식:
  ![image](/image/rollinghash.png)
  
  dece의 hash값을 구하는 것이 목적이라고 가정.
    1. adce의 해시값을 계산한다.
    2. 계산한 값에 a의 해시값을 빼고, 2를 곱한다.(자리 이동)
    3. 추가된 값인 e의 해시값을 더한다.
   
- 장점:
  - 중복되는 연산을 줄일 수 있다.
- 단점:
  - hash 값이 같다고, 모두 패턴이 같은 것은 아니다.
- 예시:
  - 문자열 비교
##### Z-알고리즘
- 정의: 문자열의 각각의 접미사와 전체 문자열의 가장 긴 공통 접두사의 길이를 빠르게 구하는 알고리즘
- 특징:
  - Z[i]는 𝑆[𝑖:](문자열 𝑆의 𝑖번째부터 끝까지)가 𝑆의 접두사와 일치하는 최대 길이를 나타낸다.
  - 문자열 길이에 비례한 시간 복잡도
  - 
- 동작 방식:
  
  dece의 hash값을 구하는 것이 목적이라고 가정.
    1. 가능한 모든 접두사를 계산한다.
    2. 0번째부터, 문자열의 길이까지 시작하는 위치를 증가시켜 부분 문자열과, 접두사의 겹치는 수를 비교한다.
    3. 결과를 배열에 저장한다.
    ```java
    import java.util.Arrays;
    public class ZAlgorithm {

        // Z-알고리즘 함수
        public static int[] calculateZ(String s) {
            int n = s.length();
            int[] z = new int[n];
            int l = 0, r = 0;

            for (int i = 1; i < n; i++) {
                if (i <= r) {
                    z[i] = Math.min(r - i + 1, z[i - l]);
                }
                while (i + z[i] < n && s.charAt(z[i]) == s.charAt(i + z[i])) {
                    z[i]++;
                }
                if (i + z[i] - 1 > r) {
                    l = i;
                    r = i + z[i] - 1;
                }
            }
            return z;
        }

        // 테스트를 위한 main 함수
        public static void main(String[] args) {
            String s = "abacaba";
            int[] zArray = calculateZ(s);

            System.out.println("Input String: " + s);
            System.out.println("Z-Array: " + Arrays.toString(zArray));
        }
    }
    ```
- 장점:
  - 빠른 시간으로 계산 가능
- 단점:
  - 순수 접두사의 관계만 계산하는 한계
- 예시:
  - 문자열 검색

## 수학 및 수치 알고리즘
#### 기초 수학 알고리즘

##### 유클리드 호제법 (Greatest Common Divisor, GCD)
- 정의: 두 정수의 최대공약수를 효율적으로 계산하는 알고리즘.
- 특징:
  - a와 b의 gcd는 a mod b의 gcd와 같다.
  - ![image](/image/gcd.png) 

- 동작 방식:
    1. a를 b로 나누어 mod 계산을 하고, 나머지가 0일 때까지 반복 계산.
   ```java
       public static int gcdRecursive(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcdRecursive(b, a % b);
    }
   ```
- 장점:
  - 간단하게 구현이 가능하다.
- 예시:
  - RSA의 키 생성
  - 두 수의 배수, 약수 계산
##### 소수 판별 (Primality Testing)
- 정의: 소수(Prime Number)는 1과 자기 자신을 제외한 다른 약수를 가지지 않는 1보다 큰 자연수
- 특징:
  - 1은 소수가 아니다.
  - 2는 유일한 짝수 소수이다.
- 동작 코드:
  숫자 N에 대해서 2 ~ N-1 까지 나누어 나머지가 0인 지 확인한다.
  ```java
  public class PrimeCheck {

      // 소수 판별 함수
      public static boolean isPrime(int n) {
          if (n <= 1) {
              return false; // 1 이하의 숫자는 소수가 아님
          }
          if (n <= 3) {
              return true; // 2와 3은 소수
          }
          if (n % 2 == 0 || n % 3 == 0) {
              return false; // 2와 3으로 나누어지면 소수가 아님
          }
          // 2와 3을 제외한 숫자
          for (int i = 5; i * i <= n; i += 6) {
              if (n % i == 0 || n % (i + 2) == 0) {
                  return false;
              }
          }
          return true;
      }
  }
  ```
   
- 예시:
  - RSA 알고리즘의 큰 소수 생성
##### 에라토스테네스의 체 (Sieve of Eratosthenes)
- 정의: 소수를 효율적으로 구하는 알고리즘으로, 2부터 𝑛까지의 자연수에서 소수를 빠르게 찾는 방법
- 특징:
  - 소수 판별과 다르게 자연수 N이 소수인지 확인하기 위해, 가운데 약수(N의 제곱근)까지만 확인하는 방법
- 동작 방식:
    1. 2부터 N까지의 모든 자연수를 나열한다
    2. 남은 수 중에서 아직 처리하지 않은 가장 작은 수 i를 찾는다
    3. 남은 수 중에서 i의 배수를 모두 제거한다(i는 제거하지 않는다)
    4. 더 이상 반복할 수 없을 때까지 2번과 3번 과정을 반복한다.
     
- 장점:
  - 소수 판별에 비해 구현
- 단점:
  - 한 번에 전체 범위를 탐색해야 하므로 범위가 작을 때는 불필요한 작업이 많음.
- 예시:
  -
#### 모듈러 연산	
##### 빠른 거듭제곱 (Fast Exponentiation)
- 정의: 큰 지수를 가진 거듭제곱을 효율적으로 계산하는 알고리즘
- 특징:
  - 지수를 분할하여 연산 횟수를 줄이는 방식
- 동작 방식:
![image](/image/fastexp.png) 
    1. 제곱 수를 a^b의 형식으로 나타낸다.
    2. b에 따라서 위의 형식과 같이 계산한다.
    3. 2번을 계속 반복한다.
```java
public class FastExponentiation {

    // 빠른 거듭제곱 (재귀 방식)
    public static long fastPow(long base, long exp) {
        if (exp == 0) {
            return 1; // a^0 = 1
        }
        if (exp % 2 == 0) {
            long half = fastPow(base, exp / 2);
            return half * half; // 짝수 지수: (a^(b/2))^2
        } else {
            return base * fastPow(base, exp - 1); // 홀수 지수: a * a^(b-1)
        }
    }

    public static void main(String[] args) {
        long base = 2;
        long exp = 10; // 2^10
        System.out.println(base + "^" + exp + " = " + fastPow(base, exp));
    }
}
```
- 장점:
  - 일반적인 거듭제곱 연산에 비해 걸리는 시간이 적음.
- 단점:
  - 알고리즘이 복잡하다.
  - 정수에만 한정되어 사용할 수 있다.
- 예시:
  - RSA
##### 중국인의 나머지 정리 (Chinese Remainder Theorem)
- 정의: 여러 개의 서로 다른 소수의 모듈러에 대해 독립적으로 주어진 나머지를 만족하는 정수를 찾는 정리
- 특징:
  - 
- 동작 방식:
![image](/image/chinese1.png) 
   1. 첫 번째 식과, 세 번째 식이 같으므로 값을 묶는다.
![image](/image/chinese2.png)
   2. x = 21 x k + 2라고 가정하고, x값을 찾는다.
![image](/image/chinese3.png) 
   3. k값을 x 값에 대입하여 x 값을 구한다. 
![image](/image/chinese4.png)
![image](/image/chinese5.png)

- 장점:
  - 여러가지 mod 계산을 효율적으로 가능.
  - 
- 단점:
  - 조건들이 서로 서로소인 경우에만 적용할 수 있음.
  - 구현이 복잡하다.
- 예시:
  - RSA 암호화 연산에서 큰 수의 거듭제곱 계산
#### 행렬 연산 (Matrix Operations)
- 정의: 주로 선형대수학에서 다뤄지며, 여러 수학적, 물리적 문제를 해결하는 데 사용.
- 특징:
  - 덧셈, 곱셈, 전치, 역행렬 등의 연산이 존재한다.
  - 주로 2차원 배열로 구현한다.
- 예시:
  - 영상의 픽셀 값을 행렬로 표현
  - 다차원 데이터를 2차원으로 표현

## 조합 및 확률 (Combinatorics and Probability)
#### 조합론
- 정의: 주어진 집합에서 원소들을 어떻게 고르고 배치할 것인지에 대한 수학적인 이론
- 특징:
  - 주어진 조건에서 가능한 경우의 수를 구하는 것
  - 수학적 모델링, 알고리즘 설계, 확률론, 통계학 등에서 중요한 역할
##### 순열 (Permutation) 및 조합 (Combination)
- 정의:
  - 순열: 주어진 집합의 원소들 중에서 순서대로 나열하는 방식
  - 조합: 주어진 집합에서 원소를 고를 때 순서를 고려하지 않고 나열하는 방식
- 특징:
  - 순열은 원소들의 순서가 중요한 경우에 사용하고, 조합은 순서가 중요하지 않은 경우에 사용한다.
- 동작 방식:
![image](/image/permutation.png) 
![image](/image/combination.png) 
    1. n은 전체 원소의 개수
    2. k는 선택할 원소의 개수
- 예시:
  - 순열은 주로 배치 문제(대진표 작성), 조합은 주로 선택 문제에서 사용(로또 번호 생성).
##### 비트마스크를 활용한 부분집합 생성
- 정의: 비트마스크는 이진수의 비트를 이용하여 여러 상태를 하나의 변수로 표현하고, 이를 조작하는 기법
- 특징:
  - 주어진 집합의 크기가 𝑛이라면, 부분집합의 수는 2^𝑛개
  - 각 부분집합을 비트로 표현하여 가능한 모든 부분집합을 생성
- 동작 방식:
    1. 000부터 시작하여 1씩 증가해나가는 연산.
  ```java
  //3비트의 수를 출력하는 코드.
  public class BitmaskExample {
    public static void main(String[] args) {
        int n = 3; // 비트 수
        int total = 1 << n; // 총 경우의 수: 2^n

        for (int i = 0; i < total; i++) {
            for (int j = 0; j < n; j++) {
                if ((i & (1 << j)) > 0) {
                    // j번째 비트가 1인 경우의 처리
                    System.out.print(1);
                } else {
                    // j번째 비트가 0인 경우의 처리
                    System.out.print(0);
                }
            }
            System.out.println(); // 한 줄 출력 후 개행
        }
    }
  }
  ```
- 장점:
  - 2^n개의 부분집합을 한 번에 생성할 수 있어 효율적임.
  - 
- 단점:
  - 큰 집합에 대해서는 연산으로 메모리 사용량이 매우 크다.
- 예시:
  - 여러가지 집합 연산

#### 확률 기반 알고리즘
##### 몬테카를로 시뮬레이션 (Monte Carlo Simulation)
- 정의: 불확실한 사건의 가능한 결과를 예측하는 수학적 기법
- 특징:
  - 반복적인 랜덤 샘플링을 통해 수치적 결과를 도출
- 동작 방식:
    1. 예측 모델을 설정하여 예측할 종속 변수와 예측을 유도할 독립 변수(입력, 위험 또는 예측 변수라고도 함)를 모두 식별
    2. 독립 변수의 확률 분포를 지정합니다. 과거 데이터 및/또는 분석가의 주관적인 판단을 사용하여 가능한 값의 범위를 정의하고 각 값에 확률 가중치를 할당
    3. 시뮬레이션을 반복적으로 실행하여 독립 변수의 임의 값을 생성한다. 무한대에 가까운 조합의 대표 샘플을 구성할 수 있을 만큼 충분한 결과가 수집될 때까지 이 작업을 수행
   
- 장점:
  - 무작위 데이터 샘플의 대규모 풀에서 여러 가지 가능한 결과와 각각의 확률을 제공
- 단점:
  - 매 계산 마다 결과 값이 다를 수 있음.
- 예시:
  - 비즈니스에서 구독 요금, 광고 비용 등의 변경의 결과를 예측하여 수익성 여부를 판단
  - 금융 시장의 주가 예측
##### 랜덤화 알고리즘 (Randomized Algorithms)


#### 기타 알고리즘	
##### 슬라이딩 윈도우 (Sliding Window)
- 정의: 유한한 크기의 윈도우(창)을 데이터나 배열, 스트림 상에서 일정 간격으로 이동시키며 데이터를 처리하는 알고리즘 설계 기법.
- 특징:
  - 교집합의 정보를 공유하고, 차이가 나는 양쪽 끝 원소만 갱신하는 방법.
  - 배열이나 리스트의 요소의 일정 범위의 값을 비교할 때 사용하면 매우 유용.
- 동작 방식:
    1. 문자열에서 특정 크기의 윈도우를 지정한다.
    2. 문자열의 첫 부분에서부터 윈도우의 크기만큼 계산한다.
    3. 윈도우의 시작 부분의 인덱스를 증가시키면서 각각 계산해나간다.
  ```java
  //최대 합을 슬라이딩 윈도우로 계산하는 코드
  public class SlidingWindowMaxSum {
    public static int findMaxSum(int[] arr, int k) {
        int n = arr.length;
        if (n < k) return -1;

        int maxSum = 0, windowSum = 0;

        // 초기 윈도우 합 계산
        for (int i = 0; i < k; i++) {
            windowSum += arr[i];
        }
        maxSum = windowSum;

        // 윈도우 슬라이딩
        for (int i = k; i < n; i++) {
            windowSum += arr[i] - arr[i - k];
            maxSum = Math.max(maxSum, windowSum);
        }

        return maxSum;
    }

    public static void main(String[] args) {
        int[] arr = {1, 4, 2, 10, 23, 3, 1, 0, 20};
        int k = 4;
        System.out.println("최대 합: " + findMaxSum(arr, k));
    }
  }

  ```
- 장점:
  - 윈도우 크기를 정적, 동적으로 모두 설정 가능하다.
  - 연속적인 구간을 한 번의 탐색으로 처리
- 단점:
  - 연속적인 구간에만 사용 가능
- 예시:
  - 부분 배열의 합, 특정 조건 만족 계싼
  - 중복 없는 부분 문자열
##### 분할-정복적 접근법
##### 유니온-파인드 (Union-Find, Disjoint Set)
- 정의:
  - 분리 집합을 구현하고 조작하는 자료 구조의 알고리즘.
- 특징:
  - 분리 집합을 합치는 union 연산과 임의의 원소가 어떤 집합에 속하는 지 찾는 find 연산을 제공
  - Tree 구조로 집합을 표현하고, 각 원소는 자신을 대표하는 루트를 가리킨다.
  - Find 연산을 최적화하는 방법으로, 트리의 경로를 압축하여 이후 찾기 연산을 더 빠르게 만든다.
  - Union 연산 시 트리의 깊이를 최소화하기 위해, 작은 트리를 큰 트리로 합친다.

- 수행 방식:
![image](/image/unionfind.png)
  - node는 4개이고, parent[node]는 node의 부모 노드 번호이다.
  - 각 step에서 union(a,b)연산을 통해 a,b 노드를 연결한다.
- 장점:
  - Find와 Union 연산이 상수 시간에 가까운 시간 복잡도를 가지므로, 대규모 데이터에 대해서도 매우 효율적이다.
  - 구현이 단순하다.
  - 집합 간 연결 여부를 추척하기에 빠름.
- 단점:
  - 원소 순서의 변경이 어려움.
  - 동적 연결성과 같은 특정 문제에서만 유용하다.
- 예시:
  -  블록체인에서의 트랜잭션 간의 관계 추적
  -  서버 간의 연결 상태를 추적하거나, 두 네트워크의 연결 여부를 확인.
  -  무방향 그래프에서 사이클을 탐지
##### 두 포인터 기법 (Two-pointer Technique)
- 정의: 1차원 배열에서 각자 다른 원소를 가리키고 있는 2개의 포인터를 조작해가면서 원하는 값을 찾을 때 까지 탐색하는 알고리즘.
- 특징:
  - 일반적으로 한 포인터는 문자열의 시작점, 다른 한 포인터는 문자열의 마지막 점에 두고, 각각 이동시킨다.
- 장점:
  - 단순한 배열 탐색으로 구현 가능.
- 단점:
  - 포인터 이동 규칙이 복잡해질 수 있음.
  - 배열이 정렬돼야 효율적임.
- 예시:
  - 문자열에서 중복된 문자 제거하기.
  - 부분 문자열의 배열 합 구하기.
##### 스위핑 기법 (Sweep Line Algorithm)
- 정의: 수평선(또는 수직선)을 한쪽 끝에서 다른 쪽 끝까지 이동하며 데이터를 처리하는 알고리즘 설계 방식.
- 특징:
  - 특정한 '이벤트'를 기준으로 선을 이동하며 상태를 업데이트.
  - 배열이나 리스트의 요소의 일정 범위의 값을 비교할 때 사용하면 매우 유용.   
- 장점:
  - 좌표 기반 문제를 효율적으로 처리 가능
- 단점:
  - 복잡성이 높다.
- 예시:
  - 선분 교차 여부 확인
  - 동시 이벤트 계산
## 알고리즘 분석	

#### 시간 복잡도 (Time Complexity)
- 정의: 
  - 알고리즘의 효율성을 판단하기 위한 지표
- 특징:
  - 알고리즘의 성능을 설명하는데 사용
  - 최악의 시나리오를 나타내는 Big-O 표기법
  - 입력 데이터 크기에 따라 수행 시간이 변함
  - 
##### Big-O, Omega, Theta Notations
 - 시간 복잡도의 표현 방법
###### Big-O
- 정의: 
  - 최악의 경우에 대한 알고리즘의 성능을 나타냄
- 특징:
  - 성능의 상한(upper bound)을 정의.
  - 알고리즘의 확장성과 최악의 성능을 분석할 때 유용.

###### Omega
- 정의: 
  - 알고리즘의 최선의 경우에 대한 하한을 나타냅니다.

- 특징:
  - 성능의 하한(lower bound)을 정의.
  - 최선의 시나리오에서 보장되는 최소 성능을 분석할 때 유용.

- ###### Theta
- 정의: 
  - 알고리즘의 성능이 상한과 하한 사이에서 정확히 제한되는 경우를 나타낸다.
- 특징:
  - 성능의 정확한 범위를 정의.
  - 알고리즘의 "정확한" 성능 분석을 제공.

##### 시간 복잡도 분석 기법

#### 공간 복잡도 (Space Complexity)
- 정의: 
  - 로그램을 실행하고 완료하는 데 필요한 메모리 공간의 양을 나타내는 척도.
- 특징:
  - 고정 공간, 가변 공간으로 구성
    - 고정 공간: 입력과 출력의 크기와 관계없는 공간으로, 코드 저장 공간, 단순 변수, 상수 등이 포함
    - 가변 공간: 문제의 특정 인스턴스에 따라 크기가 변하는 공간으로, 동적으로 할당되는 메모리
  - 공간 복잡도는 주로 가변 공간에 좌우됨.
  - Big-O 표기법으로 표현
  - 메모리 사용량이 적을수록 더 효율적인 알고리즘

#### 최선, 평균, 최악의 경우 분석

##### 최선의 경우(Best case)
- 정의: 
  - 알고리즘이 가장 효율적으로 동작하는 입력 데이터 상황을 의미한다.
- 특징:
  - 시간 복잡도가 최소가 되는 경우를 분석.
- 활용 분야:
  - 효율적인 경로 탐색
  - 정렬된 데이터 제공 시
##### 평균의 경우
- 정의: 
  - 로그램을 실행하고 완료하는 데 필요한 메모리 공간의 양을 나타내는 척도.
- 특징:
  - 고정 공간, 가변 공간으로 구성
- 활용 분야:
  - DB 검색, 웹 검색 엔진 등 일반적인 소프트웨어 설계 시 성능 최적화
##### 최악의 경우
- 정의: 
  - 알고리즘이 가장 비효율적으로 동작하는 입력 데이터 상황을 의미한다.
- 특징:
  - 일반적으로 알고리즘의 성능 보장을 위해 최악의 경우를 가장 많이 분석한다.
- 활용 분야:
  - 실시간 시스템, 금융 시스템 등 성능의 안정성이 중요한 분야.

