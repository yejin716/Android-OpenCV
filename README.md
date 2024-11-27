## OpenCV를 이용한 멀티 도서 라벨 인식 및 도서 위치 정보 알림 앱 개발 


> 도서관에서 도서(책)의 반납 작업에서 한 권씩 인식하는 바코드 인식 시스템에서
한꺼번에 많은 여러 권의 도서를 일괄 인식하여 반납 작업을 쉽게 간편하게 할 수 있는 도서 반납 인식 시스템 설계

### 데이터 수집 
- 올리브영 **스킨케어 제품** (스킨, 로션, 크림, 미스트, 에센스) 화장품 정보(이름, 브랜드, 가격, 성분, 사진, 링크, 리뷰) 크롤링
- AIhub 한국인 피부상태 측정 데이터 <https://aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=71645>
### NLP 
- 리뷰 데이터 전처리, EDA, 감성분석 진행

### 이미지 처리 
- Yolov5를 이용한 얼굴 7가지 부위별 탐지 학습 (전이학습)
  - 이미지 데이터 + 라벨링 데이터(class, bbox)
- Resnet50, Densenet201 + VGG19 (Ensemble model)를 이용한 이미지 분류
  - 피부과 전문의가 분류한 등급 라벨링 데이터 + 이미지 데이터 전이학습

### LLM을 이용한 챗봇 구현 
1. VectorDB (chromadb) 이용 - 화장품 정보, 리뷰 데이터 
2. LLM 모델 (gpt-4o-mini)
3. agent

- 전이학습한 yolo와 Ensemble model 연결하여 결과값 (관리 필요 유무) - json 파일
- json 파일 결과 - LLM에게 전달 - 답변 생성

### Streamlit 구현 
- 챗봇 개발
- sidebar + navigation 활용
- 이미지 분석 후 추천 관리 제공 + 기본 채팅 구성
  - session_state를 통해 기존 내용 history에 담아서 구성

### 데이터 수집 
- 올리브영 **스킨케어 제품** (스킨, 로션, 크림, 미스트, 에센스) 화장품 정보(이름, 브랜드, 가격, 성분, 사진, 링크, 리뷰) 크롤링
- AIhub 한국인 피부상태 측정 데이터 <https://aihub.or.kr/aihubdata/data/view.do?currMenu=&topMenu=&aihubDataSe=data&dataSetSn=71645>
### NLP 
- 리뷰 데이터 전처리, EDA, 감성분석 진행

### 이미지 처리 
- Yolov5를 이용한 얼굴 7가지 부위별 탐지 학습 (전이학습)
  - 이미지 데이터 + 라벨링 데이터(class, bbox)
- Resnet50, Densenet201 + VGG19 (Ensemble model)를 이용한 이미지 분류
  - 피부과 전문의가 분류한 등급 라벨링 데이터 + 이미지 데이터 전이학습

### LLM을 이용한 챗봇 구현 
1. VectorDB (chromadb) 이용 - 화장품 정보, 리뷰 데이터 
2. LLM 모델 (gpt-4o-mini)
3. agent

- 전이학습한 yolo와 Ensemble model 연결하여 결과값 (관리 필요 유무) - json 파일
- json 파일 결과 - LLM에게 전달 - 답변 생성

### Streamlit 구현 
- 챗봇 개발
- sidebar + navigation 활용
- 이미지 분석 후 추천 관리 제공 + 기본 채팅 구성
  - session_state를 통해 기존 내용 history에 담아서 구성
