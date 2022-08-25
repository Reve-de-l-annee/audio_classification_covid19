<h3>Caugh detection</h3>

- 주제
검사자의 음향 데이터(기침 소리)와 건강 상태 데이터(호흡기 상태, 근육통 등)들을 통해 COVID-19를 검출하는 AI 솔루션을 개발

- 주최 / 주관
주최 / 주관: 데이콘

**Final Method**
Melspectrogram feature extraction + DNN

음성데이터를 아래의 세 feature로 특성 추출한 후 DNN 모델을 사용하여 학습하였습니다.
feature1. 로그 스케일링된 melspectrogram
feature2. (운율적 소리(harmonic)+두드리는 소리(percussive)의 구성 요소)의 평균
feature3. 로그 스케일링된 melspectrogram의 델타

**Result**

![Directory Structure](https://user-images.githubusercontent.com/74871527/186582641-6cd3c4f4-868c-4397-91d0-3d33207ec96b.png)
