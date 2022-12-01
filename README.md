# Stacking Ensemble 튜토리얼

> Stacking Ensemble 튜토리얼 페이지 입니다. 본 튜토리얼에서는 개별 모델의 예측 결과를 다시 Input Data로 활용하여 최종 결과를 예측하는 Stacking Ensemble에 대해 다루어 보겠습니다.

## Stacking Ensemble

![image](https://user-images.githubusercontent.com/35906602/204995098-86646f71-8d4c-46e1-a11d-014de8974acd.png)

Stacking Ensemble이란, 개별 Base Model 들이 예측 한 결과를 다시 Meta Model의 Input Data로 활용하여 최종 결과를 예측하는 방법입니다. 일반적으로 Kaggle 등의 Competition에서 좋은 성능을 얻기 위해 주로 사용되는 방법이며, 특히 높은 일반화 성능을 기대할 수 있습니다. Stacking Ensemble에는 몇 가지 특징이 있습니다.

* 데이터의 다양한 특성을 파악하기 위해, 각 Base Model들은 서로 이질적인 것이 좋습니다.
* 이때 반드시 모델 자체가 달라야 하는 것은 아닙니다. 각 모델이 서로 다른 하이퍼 파라미터로 학습되었거나, 다른 데이터 샘플을 사용하여 학습되는 경우에도 도움이 될 수 있습니다.
* Base Model은 반드시 굉장히 높은 성능을 보일 필요는 없습니다. 성능이 다소 낮더라도 도움이 될 수 있습니다.
* 분류 모델의 경우 예측된 라벨이 아닌 확률값을 같이 학습 할 경우 최종 결과에 도움이 될 수 있습니다.
* 최종 모델로 사용되는 Meta Model의 경우 일반적으로 Logistic Regression과 같은 단순한 모델이 주로 사용됩니다. 복잡한 모델을 사용 할 경우 과적합의 위험이 있습니다. 하지만 반드시 그런 것은 아닙니다.

## CV Stacking Ensemble

하지만 위와 같은 단순한 형태의 Stacking Ensemble보다는, Cross Validation을 접목 한 방법이 더 많이 사용됩니다.

![image](https://user-images.githubusercontent.com/35906602/205006803-6ef819a5-ca73-476a-8fd4-35ce907408e0.png)

이처럼 하나의 모델에 대해 한번의 학습 및 예측을 진행하는 것이 아니라, K-Fold Cross Validation을 활용하여 더 다양한 모델을 활용하게 됩니다. 이는 모델의 과적합 위험을 낮출 수 있습니다. 

더 자세한 설명 및 실험 결과는 [Notebook](https://github.com/yunkio/Stacking_Ensemble_tutorial/blob/main/Tutorial.ipynb)을 참고 해주세요. *Sklearn*에서도 Stacking Ensemble을 지원하지만, 튜토리얼을 위해 한 단계씩 구현하였습니다.

## Sample Data를 활용한 시각화

![image](https://user-images.githubusercontent.com/35906602/205007484-b59b562c-a713-4ae7-b61c-0ec263e276d5.png)
![image](https://user-images.githubusercontent.com/35906602/205007522-e341ea32-43d9-40ba-8243-04204d19eb7d.png)

