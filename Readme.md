# RAG and LangChain simple study
참고 [모두의AI youtube](https://www.youtube.com/@AI-km1yn) 채널

### 1. LangChain
- chat gpt 의 한계를 보완한 방법
1. 인터넷 검색결과와 결합
2. CSV 파일에서 정보 얻기

### 2. LangChain 개념과 원리
- 프레임 워크, API를 통해 언어모델을 호출, 개발 등
- 언어모델을 다른 데이터 소스에 연결
- 에이전트 기능을 통해 환경과의 상호작용 가능
- 데이터 소스기반으로 대답을 하기 때문에 **할루시네이션**에 보완될 수 있다.
- 특히 최근 데이터 기반으로 **프롬프팅**에 대한 대답을 받을 수 있다

### 3. chat gpt 의 한계
- 특정 시점 기준 거짓된 답변
- 입력 토큰 수 제한
    - 사내 법규등(토큰 이 큰 문서)
- 할루시네이션으로 인한 가짜데이터 생성

### 4. 언어모델을 더 잘 활용할 수 있다!
1. fine-tuning : 기존의 모델을 weight 조정
2. N-shot Learning : N개의 출력 예시 및 용도에 맞게 출력
3. <u>**In-context Learning** : 문맥을 제시, 문맥기반으로 모델이 출력 -> LangChain</u>

### 5. Langchain 을 이용한 한계 완화
- 정보 접근 제한 : Vectorstore 기반 정보 탐색, Agent 를 활용한 검색 결합
- 토큰 제한 : TextSplitter 활용한 문서 분할
- 할루시네이션 : 주어진 문서에서만 답하도록 프롬프팅

### 6. Langchain 요소들
1. LLM : GPT, PALM-2, LLAMA, ... 등의 LLM 을 이용 (다양하게 이용가능)
2. Prompts : 지시문, 명령문 (Prompt Templates, Example Selectors(n-shot), Output Parsers)
3. Index module : LLM을 위한 문서탐색 구조화 모듈 (Document Loader, Text Splitter ...)
4. Memory : 이전 채팅을 기억하고, 이를 기반으로 대화가 가능하게 하는 모듈
5. Chain : LLM 의 연결 고리를 만들어 연속적인 LLM 호출 이 가능하도록 구성 (LLM Chain, QnA, Summarization, Retrival QnA) ...
6. Agents : 기존 템플릿으로 수행할 수 없는 작업을 가능하게 하는 모듈 (Custum Agent ... )
7. Ex: PDF 기반 챗봇
    1. 문서 업로드
    2. 문서분할
    3. 문할된 문서의 Embedding to Vectorstore, 
    4. 임베딩 검색
    5. QA chain 순서
        1. 질문 + 연관 chunck
        2. gpt로 프롬프트 생성
        3. gpt로 프롬프트 생성
        4. 결론