<h3>Caugh detection</h3>

- 주제
검사자의 음향 데이터(기침 소리)와 건강 상태 데이터(호흡기 상태, 근육통 등)들을 통해 COVID-19를 검출하는 AI 솔루션을 개발

- 주최 / 주관
주최 / 주관: 데이콘

| 프로젝트 순서 | Point | 세부 내용 |
| --- | --- | --- |
| 문제 정의 | 해결할 점, 찾아내야할 점 | 발열,두통 그리고 기침소리를 기반으로 음성/양성인 사람 찾기 |
| 데이터 수집 | 공개 데이터, 자체 수집, 제공된 데이터 | Dacon (train, test, unlabled) |
| 데이터 전처리 | 문제에 따라서 처리해야할 방향 설정 | 오디오 특징 데이터와 발열, 두통 증상 데이터 결합, 음성/양성 데이터 불균형 |
| Feature Engineering | 모델 선정 혹은 평가 지표에 큰 영향 | 오디오 특징 추출 (mel spectrogram) |
| 연관 데이터 추가 | 추가 수집 | 논문, 깃허브 |
| 알고리즘 선택 | 기본적, 현대적 | RF, XGBoost, CNN, DNN, efficientnet-b0 |
| 모델 학습 | 하이퍼파라미터,데이터 나누기 | Default, train, val, test |
| 모델 평가 | 확률 | f1-score |
| 모델 성능 향상 | 성능 지표, 하이퍼파라미터, 데이터 리터러시 재수정 | Gradient Search CV기반으로 하어퍼파라미터 설정,Optuna 활용 |

### 참고 자료

[EfficientNet 기반 기침 소리 감지 시스템 (한국차세대컴퓨팅학회, 민동욱 2021)](https://www.earticle.net/Article/A409384)
[Environmental sound classification with convolutional neural networks(IEEE, K. J. Piczak, 2015)](https://www.karolpiczak.com/papers/Piczak2015-ESC-ConvNet.pdf)
[Comparison of environmental sound classification performance of convolutional neural networks according to audio preprocessing methods(한국음향학회, 오원근, 2020)](https://www.jask.or.kr/articles/xml/RvGM/)
파이썬을 활용한 딥러닝 전이학습 (디파니안 사르카르, 러그허브 발리, 타모그나 고시 저)


### Final Method
:Melspectrogram feature extraction + DNN

 - 음성데이터를 아래의 세 feature로 특성 추출한 후 DNN 모델을 사용하여 학습하였습니다.
 - feature1. 로그 스케일링된 melspectrogram
 - feature2. (운율적 소리(harmonic)+두드리는 소리(percussive)의 구성 요소)의 평균
 - feature3. 로그 스케일링된 melspectrogram의 델타

### Result

![Directory Structure](https://user-images.githubusercontent.com/74871527/186582641-6cd3c4f4-868c-4397-91d0-3d33207ec96b.png)
