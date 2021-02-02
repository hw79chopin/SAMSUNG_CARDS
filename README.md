<h1 align="center" style="background-color:#00FEFE"><strong>🔎 삼성카드 데이터분석 공모전 (SCDC2020) </strong></h3>

<p align="center">
  <img src="https://www.fintechtimes.co.kr/data/photos/20201253/art_16092923041626_285751.jpg">
</p>


`🥇알고리즘 개발부분 1위` `#XGBoost` `#LightGBM` `#Voting` 


# 🚦 1. Introduction
- 온라인 가맹점 방문 고객 예측 알고리즘을 개발하는 공모전이다. (Track 1) [대회 포스터](https://www.samsungcard.com/personal/notice/news/UHPPCC0248M0.jsp?itgBlbdSn=5203&chnlDv=01&itgBlbdTpDvc=01)
- 최종 1위를 했다.
- 참가자: 기유진, 윤형준, 정현우

---

# 🚦 2. Algorithms and Models

### 2-1. EDA (T-sne Visualization)
- 데이터를 처음 받고서 데이터 전반의 분포와 outlier 파악을 위해 T-sne로 시각화했다. (데이터 차원이 너무 커서)
- Colab version: [T-sne.ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/EDA%20(T-sne)/T-sne.ipynb)

### 2-2. Dimensionality Reduction
- 데이터 차원이 200차원이 넘어서 차원축소를 하는 게 도움이 되는지 확인해보기 위해서 다양한 차원축소 기법을 사용하였다.
- Colab version: [Dimensionality Reduction.ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Dimensionality%20Reduction/Dimensionality%20Reduction.ipynb)

### 2-3. Hyperparameter tuning
- 모델링 방향을 정한 뒤에는 Hyperparameter tuning을 통해서 최적화시켰다. Hyperparameter tuning에는 GridSearchCV, Bayesian Optimizer를 사용하였다.
- Bayesian Optimizer로 튜닝을 하였을 때 성능이 가장 좋았다.
- Colab version: 
  - [GridSearchCV.ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Hyperparameter%20tuning/GridSearchCV.ipynb)
  - [BayesianOptimization (XGB).ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Hyperparameter%20tuning/BayesianOptimization_XGB.ipynb)  
  - [BayesianOptimization (LGBM).ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Hyperparameter%20tuning/BayesianOptimization_LGBM.ipynb)
 
### 2-4. Modeling
- 최종모델은 XGB 1개, LGBM 1개를 soft voting으로 합친 모델을 사용하였다.
- 학습에는 Google Colab Pro의 GPU (Tesla V100)를 사용하였다. 최종 모델 학습은 30시간이 넘게 걸렸다.
- LIFT와 Multiclass AUROC는 직접 함수를 만들었다. [auroc-lift.ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Modeling/aucroc-lift.ipynb)
- Colab version: [Voting Model.ipynb](https://colab.research.google.com/github/hw79chopin/SAMSUNG_CARDS/blob/master/Modeling/Voting%20Model.ipynb)

---

<h3 align="center"><strong>끗! 🙌</strong></h3>
