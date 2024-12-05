# # 과제 설명

- [2021 인공지능 그랜드 챌린지](https://www.ai-challenge.kr/) 대회에 참가하기 위해 [TUNiB](http://tunib.ai/)이 자체적으로 제작한 데이터셋을 활용하여 해당 데이터셋을 잘 분류할 수 있는 방법을 찾는 것, 그리고 분류 성능을 높이는 것을 목표로 함

# 캐글 페이지

DLthon은 다음 캐글 페이지에서 진행됩니다 !

[Aiffel Online 10th DLThon Competition](https://www.kaggle.com/t/c98f943d792d4d6098b672d8c10a7aa7)

# **DKTC**

---

## **Dataset of Korean Threatening Conversations**

한국어 위협 대화 분류 (NLU : Natural Language Understanding)

---

대화의 성격을 **위협 세부 클래스 4개 또는 일반 대화** 중 하나로 예측하는 과제

### 1. **문제 정의**

- ***학습 데이터**는 '협박', '갈취', '직장 내 괴롭힘', '기타 괴롭힘' 등 4개 클래스 각 약 1천 개로 구성*
- ***테스트 데이터**는 '협*박', '갈취', '직장 내 괴롭힘', '기타 괴롭힘', '일반 대화' 등 5개 클래스 각 1백여 개로 구성
    - train data에는 없지만, test data는 일반 대화 클래스가 존재합니다. 5개 문장을 분류할 수 있게 train data에 일반 대화 데이터셋을 추가합니다.
        - 일반대화는 **합성데이터**로 구성합니다. 다양한 프롬프트로 문장을 생성하고, 이를 학습에 활용합니다.
            - **[일반대화 클래스]**를 제외한 데이터의 추가나 외부 데이터 사용 불가(단, Augmentation은 가능)
        - Pre-trained model은 공개된 모델에 한하여 사용 가능(재현성을 위함)
        - 학습 결과를 확인하며 어떤 일반 대화 데이터셋이 성능을 높이는데 도움을 주는지 비교/기록합니다.
            - 위 기준에서 벗어나지 않는 범위 내에서 데이터셋의 구성은 자유입니다. 성능을 비교/기록해보세요 :)
            - 일반대화 데이터셋은 여러 방식으로 구할 수 있습니다. 어떤 경로를 통해 얻은 데이터셋의 성능이 좋은지 비교/기록합니다.
                - 합성데이터 생성 및 활용
                - 기 확보된 데이터 활용(추가실험)
        - 실험 결과를 Ablation study형식으로 기록합니다
        
        ```jsx
        # 일반대화 예시
        {
        	"id": {
        		"text": "이거 들어봐 와 이 노래 진짜 좋다 그치 요즘 이 것만 들어 진짜 너무 좋다 내가 요즘 듣는 것도 들어봐 음 난 좀 별론데 좋을 줄 알았는데 아쉽네 내 취향은 아닌 듯 배고프다 밥이나 먹으러 가자 그래"
        	}
        }
        ```
        

### 2. Dataset

---

- Dataset은 캐글에 업로드되어 있습니다. 구성은 다음과 같습니다.
    - Train data는 index, class, conversation등 3개의 컬럼으로 구성
    - Test data는 **index와 conversation만 제공**

### 3. 평가지표

---

- 모델이 분류한 결과와 정답 간의 f1 score로 측정

### 4. 대회 RULE

---

1. Submission파일은 리더보드에 업로드
2. 제출된 파일의 답이 맞아야 점수 부여(에러, 부분점수 등 x)
3. 일반대화를 제외한 데이터 추가 금지(augmentation은 가능)
4. DKTC의 일상대화 데이터셋은 AIHUB 등 이용해서 확보
5. 발표일 역할 분담 내용, 실험 내용, 프로젝트 진행 과정, 시각화 등 발표자료를 만들어 발표 진행
    1. 해당 발표를 기준으로 프로젝트 점수 부여 예정
    
    1. 프로젝트 평가 항목
    
    1. **데이터 EDA와 데이터 전처리가 적절하게 이뤄졌는가?**
    2. **Task에 알맞게 적절한 모델을 찾아보고 선정했는가?**
    3. **성능향상을 위해 논리적으로 접근했는가?**
    4. **결과 도출을 위해 여러가지 시도를 진행했는가?**
    5. **도출된 결론에 충분한 설득력이 있는가?**
    6. **적절한 metric을 설정하고 그 사용 근거 및 결과를 분석하였는가?**
    7. **발표가 매끄럽게 진행되었고 발표시간을 준수하였는지?**