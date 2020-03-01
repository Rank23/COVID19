# Kalman Filter을 이용한 대한민국의 코로나19 확진자/사망자/완치자 예측

이 연구는 실시간 Kalman Filter 알고리즘을 이용하여 코로나19(COVID19)의 대한민국의 확진자 추이를 예측합니다. 인구 데이터, 세계 각 지역별 확진자 수, 날씨 데이터를 입력해서 시계열 데이터 분석과 통계 알고리즘으로  확진자 추이를 예측할 것입니다. 

- [Click for Google Collab Walkthrough](https://colab.research.google.com/drive/1xC3R-vq-P4jthhOPMaMP-Bq6R7gOplsH)
- [구글 콜랩으로 코드를 실행해보세요](https://colab.research.google.com/drive/1xC3R-vq-P4jthhOPMaMP-Bq6R7gOplsH)

Ran Kremer이 Kalman Filter로 제작한 모델은 그동안 단기간의 확진자 증가 수를 비교적 정확하게 예측했습니다. 저는 Ran Kremer의 모델을 대한민국의 경우에 한정해서 확진자 수 / 사망자 수 / 완치자 수의 경향을 예측해보려고 합니다. 
- [2월 22일자 원작자 Ran Kremer의 Medium 아티클 "Kalman Filter을 이용한 코로나19 확산 예측"](https://medium.com/@rank23/using-kalman-filter-to-predict-corona-virus-spread-72d91b74cc8)
- [3월 1일자 원작자 Ran Kremer의 Medium 아티클 "코로나19 확산 예측 업데이트"](https://medium.com/analytics-vidhya/coronavirus-updated-prediction-using-kalman-filter-3ef8b7a72409)


### Short Term Forecast (국내 확진자 수 단기 예측: 1일)

![200229shortterm](./_prediction_images/200229shortterm.png)

- y축은 확진자수, x축은 날짜입니다.
- 파란색은 실제 데이터값, 노란색은 예측치입니다. 



### Long Term Forecast (국내 확진자 수 장기 예측: 30일)

![200229longterm](./_prediction_images/200229longterm.png)

- y축은 확진자수, x축은 날짜입니다.
- 파란색은 Kalman Filter 예측치입니다.



|            | '20년 2월 29일까지의 데이터를 이용한 예상 확진자 수 |
| :--------- | :-------------------------------------------------- |
| date       | South Korea_nan                                     |
| 2020-03-01 | 3166.0                                              |
| 2020-03-02 | 3783.0                                              |
| 2020-03-03 | 4005.0                                              |
| 2020-03-04 | 4199.0                                              |
| 2020-03-05 | 4630.0                                              |
| 2020-03-06 | 4927.0                                              |
| 2020-03-07 | 5402.0                                              |
| 2020-03-08 | 5864.0                                              |
| 2020-03-09 | 5864.0                                              |
| 2020-03-10 | 6494.0                                              |
| 2020-03-11 | 6494.0                                              |
| 2020-03-12 | 7154.0                                              |
| 2020-03-13 | 7215.0                                              |
| 2020-03-14 | 7215.0                                              |
| 2020-03-15 | 7215.0                                              |


## 보완할 점

- [ ] 예상 확진자 수가 날짜에 비해서 하루씩 밀림 (ex: 3월 2일 예상 확진자 수는 3783명이 아니라 4005명)
- [ ] 검사 전체 당 확진 수를 구해서 퍼센트화

## Dataset

- 코로나바이러스19로 인한 확진자, 사망자, 데이터셋은 매일 업데이트 됩니다. 
- [데이터셋의 출처는 Johns Hopkins University CSSE의 Novel Coronavirus (COVID-19) Cases입니다.](https://github.com/CSSEGISandData/COVID-19)
  - 중국의 경우는 각 성(省) 별로 인구 데이터가 나누어져 있습니다.
  - 한국을 포함한 다른 지역들은 국가 단위로 인구 데이터가 나누어져있습니다.
