# 도배 하자 질의 응답 처리 : 한솔데코 시즌2 AI 경진대회
![image](https://github.com/junhoeKu/Developing-LLM-with-dobaehaja.github.io/assets/144355794/a6c9d84b-d8ef-4a55-bddb-e4a51ff81c46)

도배 하자 도메인에 대한 질의를 바탕으로 지능적인 응답을 생성하는 AI 모델 개발입니다.

## Table of Contents

- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Data Collection](#data-collection)
- [Data Augmentation](#data-augmentation)
- [Modeling](#modeling)
- [Hyper Parameter Modification](#hyper-parameter-modification)

## Exploratory Data Analysis (EDA)

EDA는 텍스트 데이터의 특성, 분포, 형태 등 데이터의 구조를 파악하는 것을 목표로 합니다.

### Tools & Techniques Used

- **Python libraries:** Pandas, Matplotlib, Seaborn.
- **Analysis Techniques:** 기술 통계, 상관분석, 유사도 분석.

### Key Findings

- 질문 2개 / 답변 5개
- 바이트 수 : 총 600,232개의 바이트
- 음절 수 : 140,118개의 음절
- 문장 수 : 총 11,501개의 문장

## Data Collection

데이터 수집 부분에서는 Prompt Engineering과 Web Crawling을 통해 진행한 **데이터 수집 프로세스** 내용을 담았습니다.

### Data Sources

- 논문 및 레퍼런스 자료 Prompt Engineering
- 키워드 기반 Prompt Engineering
- 오늘의 집 등과 같은 도메인 사이트 Web Crawling

## Data Augmentation

데이터 증강 부분에서는 수집한 데이터를 정제, 정교화, 취합 후 검토 작업에 대한 내용을 담았습니다.

### Impact on Model Performance

- 단순히 데이터를 늘리는 것만이 정답이 아니라 판단하고 주어진 데이터를 답변에 최적화될 수 있도록 연구했습니다.
- 어떤 답변이 좋은 답변인지 확신이 없기 때문에 경우의 수를 나눠서 시도했습니다.

## Modeling

모델링 부분에서는 모델 선택의 이유, 아키텍처 세부 사항 및 학습 과정을 포함하여 사용된 모델에 대한 자세한 설명을 담았습니다.

### Models Considered

- Skt/kogpt2-base-v2 [from baseline code] : SKT에서 개발한 한국어 gpt2 모델 (125M)
- 42dot/42dot_LLM-SFT-1.3B : 국내 최고의 한영통합 언어 모델 기반의 경량 생성형 언어모델
- maywell/Synatra-42dot-1.3B : 위 모델을 기반으로 Instruction tuning된 Pretrained LLM
    -> 다양한 3B 이내 경량 모델로 실험하던 중 GPU 메모리 아웃이 나지 않은 모델

### Fine Tuning

- Prompt : LLM에 instruction을 주어 특정 task에 맞는 적절한 대답을 형성하는 것
- Fine Tuning : 사전 학습된 모델을 소규모의 데이터 세트에 대해 추가로 학습시켜 특정 작업이나 도메인에서 기능을 개선하고 성능을 향상시키는 프로세스

### LoRA

- PEFT : 적은 매개변수 학습만으로 빠른 시간에 새로운 문제를 효과적으로 해결하는 Fine-Tuning 기법
- LoRA : PEFT 방법론 중 하나로, 대부분의 매개변수 가중치는 유지하되 일부만 미세조정하는 방식
      -> 훈련 비용과 컴퓨팅 자원을 절약하면서 성능 향상 기대

### Impact on Model Performance

![KakaoTalk_20240223_012821379](https://github.com/junhoeKu/Developing-LLM-with-dobaehaja.github.io/assets/144355794/0f170bd2-bc33-40c4-ac16-9ca47c7b5455)

## Conclusion

1. 아무래도 공모전이라 주최측에서 원하는 답을 찾기가 매우 까다로웠음.(답변을 잘하기 위해서는 기본적으로 대량의 데이터를 학습시키는 것이 맞지만 데이터를 정교하게 하는 것이 더 중요했던..)
2. 같은 언어모델이라도 학습 방식에 있어 엄청난 차이가 있기 때문에 이 부분을 좀 더 공부해야 겠다고 느낌.

## License

- 아직 미완성
