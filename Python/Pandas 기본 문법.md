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
# DataFrame을 생성할 데이터 data
```

