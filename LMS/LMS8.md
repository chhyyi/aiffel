# data 어떻게 표현하면 좋을까? 배열 array와 테이블

## abstract
- 기본적인 통계 처리
- NumPy를 이용한 행렬 처리
- 각종 데이터를 array로 변환
- 구조화된 데이터? 그리고 Pandas
- EDA with pandas

## 기본적인 통계 처리
$\text{평균}=\frac{\sum_{n=1 \rightarrow N} A_i}{N}$   
$\text{표준편차}=\frac{\sqrt{\sum_{n=1 \rightarrow N} \left({A_i}-\text{평균}\right)^2}}{N}$  
$S_i \text{가 오름차순이나 내림차순으로 정렬된 상태라면,}$  
$\text{중앙값(N이 홀수일때)} = S_\frac{N+1}{2}$  
$\text{중앙값(N이 짝수일때)} = \frac{{S_\frac{i}{2}} + {S_{\frac{i}{2}+1}}}{2}$  

## NumPy
- ndarray.dtype() returns type of 'elements' (remember that every element of ndarray have same data type)
- but another examples shows that ndarray can hold various data type....  

```python
>>>> numpy.ones([3,3]) #return ndarray like numpy.zeros
 [[1.,1.,1.],
 [1.,1.,1.],
 [1.,1.,1.]]
>>>> numpy.eye(2) #return Identity Matrix.
[[1.,0.]
[0.,1.]]
```  

- broadcasting 차원이 다른 배열 사이의 산술연산(Arithmetic)
- np.random에 다양한 의사 난수. 
    + randin(), choice(), permutation(), normal(average, 표준편차, size), uniform(low, high, size)
    + size는 생성하는 난수의 개수
- ndarray.T와 numpy.transpose(ndarray, list) #일반적인 transpose가 메서드 T이고, numpy.transpose()에서는 현재의 축 순서를 마음대로 바꿀 수 있습니다.
```python3
ndarray.sum() #합
ndarray.mean() #평균
ndarray.std() #표준편차
numpy.median(ndarray) #중앙값
```

# A visual intro to Numpy and Data representation  
[이 링크를 정독하래](http://jalammar.github.io/visual-numpy/)

# image processing
```
from PIL import Image
```
- then use these methods/attributes
  + open(), size, filename, crop(x0,y0,x1,y1), resize(int,int), save('path/filename'), mode
  + open().convert('L') 

# 구조화된 데이터
-Hash
-data 내부에 자체적인 sub-structure를 가지는 데이터 like {'item':{'price':price, 'amount':amount}}

# pandas와 구조화된 데이터
- pandas.Series([value0,value1...],index=['index0','index1',....])
- pandas.Series(dictionary)
- 인덱스는 순서가 있으므로 슬라이스도 가능하다.
- Series.name, Series.index.name attributes

# pandas dataframe
- origin에서 보던 거랑 비슷하다
- Series의 name이 dataframe의 column name이 된다.
- 그런데 Series의 value에 리스트를 저장하는 방식으로 dataframe처럼 쓸 수도 있다.
- dataframe.head(), dataframe.tail(), dataframe.columns, dataframe.info(), .describe(), .isnull().sum(), .value_counts(), .sum()
- dataframe['column1'].corr('column2') : correlation between two columns. dataframe[].corr() show table for every pair of columns
- [pandas tut](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
