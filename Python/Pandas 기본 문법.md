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
df['이름']
# 이름 행만 반환
```

```python
df[['이름','나이']]
# 2차원 구조의 데이터 프레임이므로 []를 두 번 사용 (한 번 사용하면 에러)
# 이름 행과 나이 행 반환
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
# 인덱값만 출력
```

```python
df.columns
# 
```

```
