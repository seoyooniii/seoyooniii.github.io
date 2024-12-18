**1** 빅데이터개론 LMS 자료에 업로드한 `hstudent(1).csv`는 20명의 고등학생 성별, 학년, 키(cm), 몸무게(kg)를 조사한 자료입니다. 다음 작업을 수행하시오.
- `hstudent(1).csv`를 읽어서 데이터프레임 `hstudent`를 생성
- 몸무게(kg)를 키의 제곱(m)으로 나눈 값인 체질량지수에 해당하는 `bmi` 열을 데이터프레임 `hstudent`에 추가
- 몸무게가 가장 작은 학생의 체질량지수 구하기


(1) hstudent(1).csv를 읽어서 데이터프레임 hstudent를 생성

```python
import pandas as pd # pandas를 pd로 설정
```


```python
from google.colab import files
upload = files.upload() # 파일 업로드
```


```python
df_hst = pd.read_csv('hstudent(1).csv') # 데이터 프레임 생성
df_hst
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>grade</th>
      <th>height</th>
      <th>weight</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3</td>
      <td>183</td>
      <td>82</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>168</td>
      <td>52</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>1</td>
      <td>160</td>
      <td>48</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2</td>
      <td>160</td>
      <td>50</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>1</td>
      <td>160</td>
      <td>79</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1</td>
      <td>2</td>
      <td>180</td>
      <td>73</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2</td>
      <td>2</td>
      <td>183</td>
      <td>60</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
      <td>1</td>
      <td>170</td>
      <td>66</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
      <td>3</td>
      <td>170</td>
      <td>74</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>3</td>
      <td>185</td>
      <td>57</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1</td>
      <td>2</td>
      <td>165</td>
      <td>54</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2</td>
      <td>1</td>
      <td>170</td>
      <td>50</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2</td>
      <td>1</td>
      <td>152</td>
      <td>60</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2</td>
      <td>3</td>
      <td>173</td>
      <td>63</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1</td>
      <td>1</td>
      <td>145</td>
      <td>57</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1</td>
      <td>3</td>
      <td>163</td>
      <td>77</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2</td>
      <td>2</td>
      <td>178</td>
      <td>50</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2</td>
      <td>2</td>
      <td>163</td>
      <td>57</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2</td>
      <td>2</td>
      <td>168</td>
      <td>54</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2</td>
      <td>3</td>
      <td>170</td>
      <td>57</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-0ae7ba9b-85a8-412d-bd3b-fdedda263398')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

(2) 몸무게(kg)를 키의 제곱(m)으로 나눈 값인 체질량지수에 해당하는 bmi 열을 데이터프레임 hstudent에 추가


```python
df_hst['bmi'] = df_hst['weight'] / ((df_hst['height']/100)**2) # 키의 cm단위를 m단위로 변환 후, bmi를 데이터 프레임에 추가
df_hst
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>grade</th>
      <th>height</th>
      <th>weight</th>
      <th>bmi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>3</td>
      <td>183</td>
      <td>82</td>
      <td>24.485652</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>1</td>
      <td>168</td>
      <td>52</td>
      <td>18.424036</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>1</td>
      <td>160</td>
      <td>48</td>
      <td>18.750000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>2</td>
      <td>160</td>
      <td>50</td>
      <td>19.531250</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>1</td>
      <td>160</td>
      <td>79</td>
      <td>30.859375</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1</td>
      <td>2</td>
      <td>180</td>
      <td>73</td>
      <td>22.530864</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2</td>
      <td>2</td>
      <td>183</td>
      <td>60</td>
      <td>17.916331</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1</td>
      <td>1</td>
      <td>170</td>
      <td>66</td>
      <td>22.837370</td>
    </tr>
    <tr>
      <th>8</th>
      <td>1</td>
      <td>3</td>
      <td>170</td>
      <td>74</td>
      <td>25.605536</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>3</td>
      <td>185</td>
      <td>57</td>
      <td>16.654492</td>
    </tr>
    <tr>
      <th>10</th>
      <td>1</td>
      <td>2</td>
      <td>165</td>
      <td>54</td>
      <td>19.834711</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2</td>
      <td>1</td>
      <td>170</td>
      <td>50</td>
      <td>17.301038</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2</td>
      <td>1</td>
      <td>152</td>
      <td>60</td>
      <td>25.969529</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2</td>
      <td>3</td>
      <td>173</td>
      <td>63</td>
      <td>21.049818</td>
    </tr>
    <tr>
      <th>14</th>
      <td>1</td>
      <td>1</td>
      <td>145</td>
      <td>57</td>
      <td>27.110583</td>
    </tr>
    <tr>
      <th>15</th>
      <td>1</td>
      <td>3</td>
      <td>163</td>
      <td>77</td>
      <td>28.981143</td>
    </tr>
    <tr>
      <th>16</th>
      <td>2</td>
      <td>2</td>
      <td>178</td>
      <td>50</td>
      <td>15.780836</td>
    </tr>
    <tr>
      <th>17</th>
      <td>2</td>
      <td>2</td>
      <td>163</td>
      <td>57</td>
      <td>21.453574</td>
    </tr>
    <tr>
      <th>18</th>
      <td>2</td>
      <td>2</td>
      <td>168</td>
      <td>54</td>
      <td>19.132653</td>
    </tr>
    <tr>
      <th>19</th>
      <td>2</td>
      <td>3</td>
      <td>170</td>
      <td>57</td>
      <td>19.723183</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-0fde97e9-8331-4245-af0b-0667d6c188fd')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">


    }

   
  
(3) 몸무게가 가장 작은 학생의 체질량지수 구하기


```python
df_hst2 = df_hst[df_hst.weight == df_hst['weight'].min()] # 가장 작은 몸무게를 가진 학생의 행 추출
df_hst2
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gender</th>
      <th>grade</th>
      <th>height</th>
      <th>weight</th>
      <th>bmi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>1</td>
      <td>160</td>
      <td>48</td>
      <td>18.75</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-397ef851-70c8-4eab-8e1b-205c92f50295')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>



**2** 수업 시간에 사용한 `train-data-01.csv`를 사용하여 다음에 답하시오.
- 서울 출발 대전 도착 열차의 날짜별 평균 탑승객 수 시계열 그래프 그리고, 평균 탑승객 수가 가장 많은 날짜를 구하시오.
- 서울 출발 대전 도착 열차의 요일별 평균 탑승객 수 계산하여 표로 나타내시오.

(1) 서울 출발 대전 도착 열차의 날짜별 평균 탑승객 수 시계열 그래프 그리고, 평균 탑승객 수가 가장 많은 날짜를 구하시오.


```python
url ="https://raw.githubusercontent.com/UOS-Bigdata/bigdatabook/main/data/train-data-01.csv" # Github로부터 url 불러오기
```


```python
df_train = pd.read_csv(url) # url 파일 읽기
df_train
```



<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>NUM_PASSENGER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>20190701</td>
      <td>서울</td>
      <td>대전</td>
      <td>106.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>20190702</td>
      <td>서울</td>
      <td>대전</td>
      <td>113.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20190703</td>
      <td>서울</td>
      <td>대전</td>
      <td>146.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20190704</td>
      <td>서울</td>
      <td>대전</td>
      <td>84.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>20190705</td>
      <td>서울</td>
      <td>대전</td>
      <td>105.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>1764</th>
      <td>6</td>
      <td>20190726</td>
      <td>울산</td>
      <td>부산</td>
      <td>10.0</td>
    </tr>
    <tr>
      <th>1765</th>
      <td>6</td>
      <td>20190727</td>
      <td>울산</td>
      <td>부산</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>1766</th>
      <td>6</td>
      <td>20190728</td>
      <td>울산</td>
      <td>부산</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>1767</th>
      <td>6</td>
      <td>20190729</td>
      <td>울산</td>
      <td>부산</td>
      <td>12.0</td>
    </tr>
    <tr>
      <th>1768</th>
      <td>6</td>
      <td>20190730</td>
      <td>울산</td>
      <td>부산</td>
      <td>11.0</td>
    </tr>
  </tbody>
</table>
<p>1769 rows × 5 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-b76f2c90-640d-4ec0-a777-4c37f74bbe15')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>




```python
c1 = df_train.STATION_DEPART == '서울'# 출발역이 서울일 때
c2 = df_train.STATION_ARRV == '대전' # 도착역이 대전일 때
```


```python
c12 = c1 & c2 # &를 사용하여 조건을 묶어줌.
```


```python
df_train2 = df_train[c12] # 서울 출발 대전 도착 열차 추출
df_train2
```


<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>NUM_PASSENGER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>20190701</td>
      <td>서울</td>
      <td>대전</td>
      <td>106.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>20190702</td>
      <td>서울</td>
      <td>대전</td>
      <td>113.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20190703</td>
      <td>서울</td>
      <td>대전</td>
      <td>146.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20190704</td>
      <td>서울</td>
      <td>대전</td>
      <td>84.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>20190705</td>
      <td>서울</td>
      <td>대전</td>
      <td>105.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>955</th>
      <td>6</td>
      <td>20190726</td>
      <td>서울</td>
      <td>대전</td>
      <td>98.0</td>
    </tr>
    <tr>
      <th>956</th>
      <td>6</td>
      <td>20190727</td>
      <td>서울</td>
      <td>대전</td>
      <td>92.0</td>
    </tr>
    <tr>
      <th>957</th>
      <td>6</td>
      <td>20190728</td>
      <td>서울</td>
      <td>대전</td>
      <td>131.0</td>
    </tr>
    <tr>
      <th>958</th>
      <td>6</td>
      <td>20190729</td>
      <td>서울</td>
      <td>대전</td>
      <td>77.0</td>
    </tr>
    <tr>
      <th>959</th>
      <td>6</td>
      <td>20190730</td>
      <td>서울</td>
      <td>대전</td>
      <td>75.0</td>
    </tr>
  </tbody>
</table>
<p>90 rows × 5 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-af0fbccb-eb69-49d0-a5e1-4685cad99870')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

 

```python
df_train2['DATE2'] = pd.to_datetime(df_train2['DATE'], format = '%Y%m%d') # 날짜 형식을 가진 변수 DATE2 추가
df_train2
```



<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>NUM_PASSENGER</th>
      <th>DATE2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>20190701</td>
      <td>서울</td>
      <td>대전</td>
      <td>106.0</td>
      <td>2019-07-01</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>20190702</td>
      <td>서울</td>
      <td>대전</td>
      <td>113.0</td>
      <td>2019-07-02</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20190703</td>
      <td>서울</td>
      <td>대전</td>
      <td>146.0</td>
      <td>2019-07-03</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20190704</td>
      <td>서울</td>
      <td>대전</td>
      <td>84.0</td>
      <td>2019-07-04</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>20190705</td>
      <td>서울</td>
      <td>대전</td>
      <td>105.0</td>
      <td>2019-07-05</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>955</th>
      <td>6</td>
      <td>20190726</td>
      <td>서울</td>
      <td>대전</td>
      <td>98.0</td>
      <td>2019-07-26</td>
    </tr>
    <tr>
      <th>956</th>
      <td>6</td>
      <td>20190727</td>
      <td>서울</td>
      <td>대전</td>
      <td>92.0</td>
      <td>2019-07-27</td>
    </tr>
    <tr>
      <th>957</th>
      <td>6</td>
      <td>20190728</td>
      <td>서울</td>
      <td>대전</td>
      <td>131.0</td>
      <td>2019-07-28</td>
    </tr>
    <tr>
      <th>958</th>
      <td>6</td>
      <td>20190729</td>
      <td>서울</td>
      <td>대전</td>
      <td>77.0</td>
      <td>2019-07-29</td>
    </tr>
    <tr>
      <th>959</th>
      <td>6</td>
      <td>20190730</td>
      <td>서울</td>
      <td>대전</td>
      <td>75.0</td>
      <td>2019-07-30</td>
    </tr>
  </tbody>
</table>
<p>90 rows × 6 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-769aafd3-aa84-4d7f-833b-2b88c11c0a27')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>





```python
summary_data = df_train2.groupby('DATE2').mean() # 날짜를 기준으로 그룹화 후, 평균계산
summary_data
```

  
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>NUM_PASSENGER</th>
    </tr>
    <tr>
      <th>DATE2</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2019-07-01</th>
      <td>4.333333</td>
      <td>20190701.0</td>
      <td>91.000000</td>
    </tr>
    <tr>
      <th>2019-07-02</th>
      <td>4.333333</td>
      <td>20190702.0</td>
      <td>99.666667</td>
    </tr>
    <tr>
      <th>2019-07-03</th>
      <td>4.333333</td>
      <td>20190703.0</td>
      <td>132.000000</td>
    </tr>
    <tr>
      <th>2019-07-04</th>
      <td>4.333333</td>
      <td>20190704.0</td>
      <td>116.000000</td>
    </tr>
    <tr>
      <th>2019-07-05</th>
      <td>4.333333</td>
      <td>20190705.0</td>
      <td>108.666667</td>
    </tr>
    <tr>
      <th>2019-07-06</th>
      <td>4.333333</td>
      <td>20190706.0</td>
      <td>108.000000</td>
    </tr>
    <tr>
      <th>2019-07-07</th>
      <td>4.333333</td>
      <td>20190707.0</td>
      <td>110.333333</td>
    </tr>
    <tr>
      <th>2019-07-08</th>
      <td>4.333333</td>
      <td>20190708.0</td>
      <td>100.000000</td>
    </tr>
    <tr>
      <th>2019-07-09</th>
      <td>4.333333</td>
      <td>20190709.0</td>
      <td>135.000000</td>
    </tr>
    <tr>
      <th>2019-07-10</th>
      <td>4.333333</td>
      <td>20190710.0</td>
      <td>119.000000</td>
    </tr>
    <tr>
      <th>2019-07-11</th>
      <td>4.333333</td>
      <td>20190711.0</td>
      <td>117.333333</td>
    </tr>
    <tr>
      <th>2019-07-12</th>
      <td>4.333333</td>
      <td>20190712.0</td>
      <td>97.666667</td>
    </tr>
    <tr>
      <th>2019-07-13</th>
      <td>4.333333</td>
      <td>20190713.0</td>
      <td>103.000000</td>
    </tr>
    <tr>
      <th>2019-07-14</th>
      <td>4.333333</td>
      <td>20190714.0</td>
      <td>103.666667</td>
    </tr>
    <tr>
      <th>2019-07-15</th>
      <td>4.333333</td>
      <td>20190715.0</td>
      <td>111.000000</td>
    </tr>
    <tr>
      <th>2019-07-16</th>
      <td>4.333333</td>
      <td>20190716.0</td>
      <td>118.000000</td>
    </tr>
    <tr>
      <th>2019-07-17</th>
      <td>4.333333</td>
      <td>20190717.0</td>
      <td>96.000000</td>
    </tr>
    <tr>
      <th>2019-07-18</th>
      <td>4.333333</td>
      <td>20190718.0</td>
      <td>131.333333</td>
    </tr>
    <tr>
      <th>2019-07-19</th>
      <td>4.333333</td>
      <td>20190719.0</td>
      <td>98.000000</td>
    </tr>
    <tr>
      <th>2019-07-20</th>
      <td>4.333333</td>
      <td>20190720.0</td>
      <td>110.666667</td>
    </tr>
    <tr>
      <th>2019-07-21</th>
      <td>4.333333</td>
      <td>20190721.0</td>
      <td>105.000000</td>
    </tr>
    <tr>
      <th>2019-07-22</th>
      <td>4.333333</td>
      <td>20190722.0</td>
      <td>110.000000</td>
    </tr>
    <tr>
      <th>2019-07-23</th>
      <td>4.333333</td>
      <td>20190723.0</td>
      <td>118.000000</td>
    </tr>
    <tr>
      <th>2019-07-24</th>
      <td>4.333333</td>
      <td>20190724.0</td>
      <td>123.000000</td>
    </tr>
    <tr>
      <th>2019-07-25</th>
      <td>4.333333</td>
      <td>20190725.0</td>
      <td>117.333333</td>
    </tr>
    <tr>
      <th>2019-07-26</th>
      <td>4.333333</td>
      <td>20190726.0</td>
      <td>94.000000</td>
    </tr>
    <tr>
      <th>2019-07-27</th>
      <td>4.333333</td>
      <td>20190727.0</td>
      <td>87.333333</td>
    </tr>
    <tr>
      <th>2019-07-28</th>
      <td>4.333333</td>
      <td>20190728.0</td>
      <td>92.000000</td>
    </tr>
    <tr>
      <th>2019-07-29</th>
      <td>4.333333</td>
      <td>20190729.0</td>
      <td>84.333333</td>
    </tr>
    <tr>
      <th>2019-07-30</th>
      <td>4.333333</td>
      <td>20190730.0</td>
      <td>94.000000</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-a9c6c14d-1eff-487d-9633-f2de87564d0c')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>





```python
summary_data.reset_index(inplace = True ) # DATE2를 다시 열로 만들어줌
```


```python
summary_data.plot(x = 'DATE2', y = 'NUM_PASSENGER') # 시계열 그래프 생성
```



    
![png](HW5_%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%89%E1%85%A5%E1%84%8B%E1%85%B2%E1%86%AB_files/HW5_%E1%84%8C%E1%85%A5%E1%86%BC%E1%84%89%E1%85%A5%E1%84%8B%E1%85%B2%E1%86%AB_27_1.png)
    


2019-07-09의 평균 탒승객 수가 가장 많아보임.

-> max()를 활용해 확인


```python
max_NUM_PASSENGER = summary_data[summary_data['NUM_PASSENGER'] == summary_data['NUM_PASSENGER'].max()] # NUM_PASSENGER가 최댓값에 해당하는 행 추출
max_NUM_PASSENGER
```





  <div id="df-6627494d-219c-4ddb-ad72-ea1492a61545" class="colab-df-container">
    <div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>DATE2</th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>NUM_PASSENGER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8</th>
      <td>2019-07-09</td>
      <td>4.333333</td>
      <td>20190709.0</td>
      <td>135.0</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-6627494d-219c-4ddb-ad72-ea1492a61545')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-6627494d-219c-4ddb-ad72-ea1492a61545 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-6627494d-219c-4ddb-ad72-ea1492a61545');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


  <div id="id_ec29ff0d-3b1e-4f6e-aaf0-62d151135ccd">
    <style>
      .colab-df-generate {
        background-color: #E8F0FE;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        display: none;
        fill: #1967D2;
        height: 32px;
        padding: 0 0 0 0;
        width: 32px;
      }

      .colab-df-generate:hover {
        background-color: #E2EBFA;
        box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
        fill: #174EA6;
      }

      [theme=dark] .colab-df-generate {
        background-color: #3B4455;
        fill: #D2E3FC;
      }

      [theme=dark] .colab-df-generate:hover {
        background-color: #434B5C;
        box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
        filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
        fill: #FFFFFF;
      }
    </style>
    <button class="colab-df-generate" onclick="generateWithVariable('max_NUM_PASSENGER')"
            title="Generate code using this dataframe."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M7,19H8.4L18.45,9,17,7.55,7,17.6ZM5,21V16.75L18.45,3.32a2,2,0,0,1,2.83,0l1.4,1.43a1.91,1.91,0,0,1,.58,1.4,1.91,1.91,0,0,1-.58,1.4L9.25,21ZM18.45,9,17,7.55Zm-12,3A5.31,5.31,0,0,0,4.9,8.1,5.31,5.31,0,0,0,1,6.5,5.31,5.31,0,0,0,4.9,4.9,5.31,5.31,0,0,0,6.5,1,5.31,5.31,0,0,0,8.1,4.9,5.31,5.31,0,0,0,12,6.5,5.46,5.46,0,0,0,6.5,12Z"/>
  </svg>
    </button>
    <script>
      (() => {
      const buttonEl =
        document.querySelector('#id_ec29ff0d-3b1e-4f6e-aaf0-62d151135ccd button.colab-df-generate');
      buttonEl.
```python
max_NUM_PASSENGER['DATE2'] # 평균 탑승객 수가 가장 많은 날짜
```




    8   2019-07-09
    Name: DATE2, dtype: datetime64[ns]



(2) 서울 출발 대전 도착 열차의 요일별 평균 탑승객 수 계산하여 표로 나타내시오


```python
df_train2['DAYOFWEEK'] = df_train2['DATE2'].dt.dayofweek # 요일 변수 추가
df_train2
```


  <div id="df-5c49d25e-d1a5-4c04-ada2-e4e8d32dbb4d" class="colab-df-container">
    <div>
      
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>TRAIN_NO</th>
      <th>DATE</th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>NUM_PASSENGER</th>
      <th>DATE2</th>
      <th>DAYOFWEEK</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2</td>
      <td>20190701</td>
      <td>서울</td>
      <td>대전</td>
      <td>106.0</td>
      <td>2019-07-01</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>20190702</td>
      <td>서울</td>
      <td>대전</td>
      <td>113.0</td>
      <td>2019-07-02</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>20190703</td>
      <td>서울</td>
      <td>대전</td>
      <td>146.0</td>
      <td>2019-07-03</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20190704</td>
      <td>서울</td>
      <td>대전</td>
      <td>84.0</td>
      <td>2019-07-04</td>
      <td>3</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2</td>
      <td>20190705</td>
      <td>서울</td>
      <td>대전</td>
      <td>105.0</td>
      <td>2019-07-05</td>
      <td>4</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>955</th>
      <td>6</td>
      <td>20190726</td>
      <td>서울</td>
      <td>대전</td>
      <td>98.0</td>
      <td>2019-07-26</td>
      <td>4</td>
    </tr>
    <tr>
      <th>956</th>
      <td>6</td>
      <td>20190727</td>
      <td>서울</td>
      <td>대전</td>
      <td>92.0</td>
      <td>2019-07-27</td>
      <td>5</td>
    </tr>
    <tr>
      <th>957</th>
      <td>6</td>
      <td>20190728</td>
      <td>서울</td>
      <td>대전</td>
      <td>131.0</td>
      <td>2019-07-28</td>
      <td>6</td>
    </tr>
    <tr>
      <th>958</th>
      <td>6</td>
      <td>20190729</td>
      <td>서울</td>
      <td>대전</td>
      <td>77.0</td>
      <td>2019-07-29</td>
      <td>0</td>
    </tr>
    <tr>
      <th>959</th>
      <td>6</td>
      <td>20190730</td>
      <td>서울</td>
      <td>대전</td>
      <td>75.0</td>
      <td>2019-07-30</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
<p>90 rows × 7 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-5c49d25e-d1a5-4c04-ada2-e4e8d32dbb4d')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">



```python
train_group = df_train2[ [ 'STATION_DEPART', 'STATION_ARRV','DAYOFWEEK','NUM_PASSENGER']] # 요일, 출발역, 도착역 변수만 뽑아줌
train_group
```





  <div id="df-c3639823-c006-4ea1-af76-f5234197ec75" class="colab-df-container">
    <div>



<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>DAYOFWEEK</th>
      <th>NUM_PASSENGER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>서울</td>
      <td>대전</td>
      <td>0</td>
      <td>106.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>서울</td>
      <td>대전</td>
      <td>1</td>
      <td>113.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>서울</td>
      <td>대전</td>
      <td>2</td>
      <td>146.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서울</td>
      <td>대전</td>
      <td>3</td>
      <td>84.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>서울</td>
      <td>대전</td>
      <td>4</td>
      <td>105.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>955</th>
      <td>서울</td>
      <td>대전</td>
      <td>4</td>
      <td>98.0</td>
    </tr>
    <tr>
      <th>956</th>
      <td>서울</td>
      <td>대전</td>
      <td>5</td>
      <td>92.0</td>
    </tr>
    <tr>
      <th>957</th>
      <td>서울</td>
      <td>대전</td>
      <td>6</td>
      <td>131.0</td>
    </tr>
    <tr>
      <th>958</th>
      <td>서울</td>
      <td>대전</td>
      <td>0</td>
      <td>77.0</td>
    </tr>
    <tr>
      <th>959</th>
      <td>서울</td>
      <td>대전</td>
      <td>1</td>
      <td>75.0</td>
    </tr>
  </tbody>
</table>
<p>90 rows × 4 columns</p>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-c3639823-c006-4ea1-af76-f5234197ec75')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>



```python
summary_data2 = train_group.groupby(['STATION_DEPART','STATION_ARRV','DAYOFWEEK']).mean() # 요일, 출발역, 도착역으로 그룹화 후, 평균값 도출
summary_data2
```





  <div id="df-e75c548e-1b0b-43e0-b8b0-4782756a8d14" class="colab-df-container">
    <div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th></th>
      <th></th>
      <th>NUM_PASSENGER</th>
    </tr>
    <tr>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>DAYOFWEEK</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="7" valign="top">서울</th>
      <th rowspan="7" valign="top">대전</th>
      <th>0</th>
      <td>99.266667</td>
    </tr>
    <tr>
      <th>1</th>
      <td>112.933333</td>
    </tr>
    <tr>
      <th>2</th>
      <td>117.500000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>120.500000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>99.583333</td>
    </tr>
    <tr>
      <th>5</th>
      <td>102.250000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>102.750000</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-e75c548e-1b0b-43e0-b8b0-4782756a8d14')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">


```python
summary_data2.reset_index(inplace=True) # STATION_DEPART, STATION_ARRV, DAYOFWEEK를 다시 열로 만들어줌
summary_data2 # 결과표
```





  <div id="df-a6590b73-86fc-4cd0-9a6b-246c2eb0cbcc" class="colab-df-container">
    <div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>STATION_DEPART</th>
      <th>STATION_ARRV</th>
      <th>DAYOFWEEK</th>
      <th>NUM_PASSENGER</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>서울</td>
      <td>대전</td>
      <td>0</td>
      <td>99.266667</td>
    </tr>
    <tr>
      <th>1</th>
      <td>서울</td>
      <td>대전</td>
      <td>1</td>
      <td>112.933333</td>
    </tr>
    <tr>
      <th>2</th>
      <td>서울</td>
      <td>대전</td>
      <td>2</td>
      <td>117.500000</td>
    </tr>
    <tr>
      <th>3</th>
      <td>서울</td>
      <td>대전</td>
      <td>3</td>
      <td>120.500000</td>
    </tr>
    <tr>
      <th>4</th>
      <td>서울</td>
      <td>대전</td>
      <td>4</td>
      <td>99.583333</td>
    </tr>
    <tr>
      <th>5</th>
      <td>서울</td>
      <td>대전</td>
      <td>5</td>
      <td>102.250000</td>
    </tr>
    <tr>
      <th>6</th>
      <td>서울</td>
      <td>대전</td>
      <td>6</td>
      <td>102.750000</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-a6590b73-86fc-4cd0-9a6b-246c2eb0cbcc')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>



