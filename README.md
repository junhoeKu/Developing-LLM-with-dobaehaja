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

- Skt/kogpt2-base-v2 [from baseline code]

### Training Process

- Details on the training process, including splitting of data, cross-validation methods used, and evaluation metrics.

## Hyper Parameter Modification

Explanation of the hyperparameter tuning process to optimize model performance.

### Methods Used for Hyperparameter Tuning

- Grid Search, Random Search, Bayesian Optimization, etc.

### Impact on Model Performance

- Before and after comparison of model performance metrics to highlight the impact of hyperparameter tuning.

## Conclusion

Summarize the key outcomes of the project, including the final model performance, lessons learned, and potential next steps for future work.

## How to Use

Instructions for others on how to use this project for their own data or as a basis for further exploration.

## Contributing

Guidelines for contributing to this project, if open for contributions.

## License

Specify the license under which the project is released.
