# ProjectDL
2022 부산시 빅데이터 분석가 과정 - 딥러닝 미니 프로젝트

## 🖥️ 프로젝트 소개
사용자의 입력 기반으로 감정 분석 및 플레이리스트 추천 서비스.
단순한 플레이리스트 추천이 아닌 사용자의 감정에 기반한 플레이리스트를 추천해줌으로써 감정 해소 및 치유 효과를 기대<br>
[발표 PPT](https://github.com/leesominn/ProjectDL/blob/main/projectDL_presentation.pdf)
<br>

### 🕰️ 개발 기간
* 22.09.14일 - 22.10.21일

### 🧑‍🤝‍🧑 팀원 구성
 - 이소민 : 말뭉치 데이터 수집, 추천용 플레이리스트 전처리 및 시각화, 모델 학습 및 튜닝
 - 김소희 : 멜론 플레이리스트 데이터 수집, 감정예측용 데이터 전처리, 모델 예측

### ⚙️ 기술 스택 및 개발 환경
  - `Python`
  - `Pandas`
  - `Matplotlib`
  - `Colab`
  - `Vscode`

## 📌 프로젝트 과정
#### 데이터 수집
  - 말뭉치 데이터 수집 : 감정 분석을 위해 단발성/연속적 대화 데이터셋 약 9만 문장 수집 (출처 : AI-Hub)
  - 멜론 플레이리스트 데이터 수집 : 플레이리스트 수집을 위해 멜론 플레이리스트 약 11만 건 수집 (출처 : Kakao Arena)

#### 데이터 전처리 및 분석
  - 말뭉치 데이터 전처리 [코드 링크](https://github.com/leesominn/ProjectDL/blob/main/preprocessing/emotion_data_6label.ipynb)
   - 단발성/연속적 대화 데이터셋 결합
   - 원천 분류 중 '중립'라벨 및 오타 처리된 감정 제거 -> 6가지 감정만 사용(공포, 혐오, 놀람, 분노, 슬픔, 행복)
  - 플레이리스트 데이터 전처리 [코드 링크](https://github.com/leesominn/ProjectDL/tree/main/preprocessing)
    - 상위 노출 태그만 추출
    - 추출된 태그 중 감정 관련 태그를 제외한 장르 태그 제거
    - 태그를 감정과 매칭시켜 분류
    - 플레이리스트 태그 상위 노출 태그를 확인하기 위해 그래프로 시각화 진행, 라벨링에 활용
    
#### 모델링 [코드 링크](https://github.com/leesominn/ProjectDL/tree/main/modeling)
  - Tensorflow와 다중감정 분류를 위해 Kobert 모델 활용
  - 모델 파라미터 커스텀 및 튜닝
  - 모델 예측 : 학습된 모델의 감정별 평균 정확도 확인, 예측 결과를 감정-확률 형태로 구현
