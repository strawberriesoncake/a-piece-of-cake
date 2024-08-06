```python
data = {
		'이름' : ['정민수', '최온', '달비', '무로', '참'],
		'나이' : [410, 373, None, 38, 26],
		'신장' : [185, 163, 50, 60, 40],
		'밥' : ["ramen", "curry", "orijen", "Josera", "josera"]
}
```

```python
import pandas as pd
# 판다스를 pd라는 약칭으로 Import

df = pd.DataFrame(data)
# DataFrame을 생성할 데이터를 df로 명명
```

```python
df.to_csv('family.csv', encoding='utf-8-sig')
# family.csv 파일로 저장
```

```python
df = pd.read_csv('family.csv')
# family.csv 파일 불러오기
```

```python
df['이름']
# '이름' 컬럼 출력
```

```python
df[['이름','나이']]
# 2차원 구조의 데이터 프레임이므로 []를 두 번 사용 (한 번 사용하면 에러)
# '이름' 컬럼과 '나이' 컬럼 출력
```

```python
df = pd.DataFrame(data, columns = ['이름','나이','신장'])
# '이름', '나이', '신장' 컬럼만 출력
```

```python
df = pd.DataFrame(data, index = ['1','2','3','4','5'])
# 인덱스값에 1,2,3,4,5를 레이블 부여
```

```python
df.index.name="서열"
# 인덱스 제목에 '서열' 레이블 부여
```

```python
df.index
# 인덱스 값만 출력
```

```python
df.columns
# 컬럼 값만 출력
```

```python
df.values
# 값을 출력
```

```python
df.shape
# 컬럼, 로우의 개수를 출력
```

```python
df.describe()
# 데이터프레임의 전반적인 통계
```

```python
df.info()
# 데이터프레임의 전반적인 정보
```

```python
df.head(n)
# 데이터프레임의 상단부터 n개 로우 출력
```

```python
df.tail(n)
# 데이터프레임의 하단부터 n개 로우 출력
```

```python
df[df.colums[3]]
# 3번 인덱스 컬럼 출력
```

```python
df['나이'].describe()
# '나이' 컬럼의 전반적인 통계
```

```python
df['나이'].mean()
# '나이' 컬럼의 평균값
```

```python
df['신장'].nlargest()
# '나이' 컬럼을 큰 값부터 정렬
```

```python
df['이름'][0:2]
# '이름' 컬럼을 0:2로 슬라이싱
```

```python
df.loc['1']
# 1번 컬럼에 위치한 값 출력
```

```python
df.loc[1','나이']
# 1번 컬럼과 '나이' 로우 좌표의 값 출력
```

```python
df.loc[['1','2'],['이름','밥']]
# 1,2번 컬럼과 '이름','밥' 로우 좌표의 값 출력
```

```python
df.iloc[1]
# 1번 인덱스 컬럼에 위치한 값 출력
```

```python
df.iloc[:]
# 모든 컬럼과 로우의 값 출력
```

``` python
df.iloc[1,3]
# 1번 인덱스의 컬럼과 3번 인덱스의 로우 좌표의 값 출력
```

```python
df['체중'] = [83, 56, 6, 5, 5]
# '체중' 컬럼 추가 및 속성값 부여
```

```python
df['출신지']= ''
# '출신지' 컬럼 추가 및 속성값은 공백으로 지정
```

```python
del df['출신지']
# '출신지' 컬럼 삭제
```

```python
df['나이']>100
# 불린 값 출력
```

```python
df[df['나이']>100]
# '나이'가 100 이상인 로우만으로 이루어진 데이터프레임 출력
```

```python
df.loc[df['나이']>100,'신장']
# '나이'가 100 이상인 로우만으로 이루어진 데이터프레임에서 '신장' 컬럼 출력
```

```python
df.loc[df['나이']>100,['신장','밥','체중']]
# '나이'가 100 이상인 로우만으로 이루어진 데이터프레임에서 '신장','밥','체중' 컬럼 출력
```

```python
df['출신지'] = ['서울','부산','대구','충무로','파주']
# '출신지' 컬럼 추가 및 속성값 부여
```

```python
df['밥'].replace({'라멘':'ramen','카레':'curry'})
# '밥' 컬럼의 '라멘' 값을 'ramen'으로, '카레' 값을 'curry'로 대체하여 출력
```

```python
df['밥'].replace({'라멘':'ramen','카레':'curry'},inplace=True)
# '밥' 컬럼의 '라멘' 값을 'ramen'으로, '카레' 값을 'curry'로 덮어씀
```

```python
df['밥'].str.lower()
# '밥' 컬럼의 문자열을 소문자로 변환
```

```python
df['밥'].str.upper()
# '밥' 컬럼의 문자열을 대문자로 변환
```

```python
df['키빼몸']=df['신장']-df['체중']
# '키빼몸' 컬럼 추가 및 속성값 부여
# 파생 변수
```

```python
df['직업']='캔따개'
# '직업' 컬럼 추가 및 속성값 일괄 부여
```

```python
df.loc[df['신장']<100,'직업']='고양이'
# '신장'이 100 미만인 로우의 '직업'을 '고양이'로 지정
```

```python
df.drop(index=1)
# 로우를 삭제하여 출력
```

```python
df.sort_values('나이')
# '나이' 컬럼을 기준으로 오름차순 정렬
```

```python
df.sort_values(['나이','체중'])
# '나이' 컬럼을 기준으로 오름차순 정렬 후 '체중' 컬럼을 기준으로 오름차순 정렬
```

```python
df.sort_index()
# '인덱스'를 기준으로 오름차순 정렬
```

```python
df.sort_values('나이', ascending=False)
# '나이' 컬럼을 기준으로 내림차순 정렬
```

```python
df.groupby('밥').mean()
# '밥' 컬럼을 기준으로 그룹핑한 전체 로우의 평균값
```

```python
df.groupby('밥').size()
# '밥' 컬럼을 기준으로 그룹핑하여 각 그룹 개수 출력
```

```python
df.groupby('밥')['체중'].mean()
# '밥' 컬럼을 기준으로 그룹핑하여 각 그룹 평균 출력
```

```python
df.groupby('밥').get_group('JOSERA')
# '밥' 컬럼을 기준으로 그룹핑하여 값이 'JOSERA'인 로우만 출력
```