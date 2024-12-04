# RAG and LangChain simple study
참고 [모두의AI youtube](https://www.youtube.com/@AI-km1yn) 채널

### RAG (Retrieval Augmented Generation)
![RAG](img/Langchain_retrieval.png)

### 전체 파일 구조
[📂파일 구조](./list.md)

### 1. LangChain
- ChatGPT 한계 보완: 
  1. 인터넷 검색결과 결합
  2. CSV, pdf, txt 등의 docs 파일 정보 활용

### 2. LangChain 개념
- 데이터 소스와 연결, 에이전트로 환경 상호작용
- 할루시네이션 보완, 최근 데이터로 프롬프트 대답 가능

### 3. ChatGPT 한계
- 거짓된 답변, 토큰 제한, 할루시네이션

### 4. 언어모델 활용법
1. Fine-tuning
2. N-shot Learning : 모델에게 n 개의 예시 제공
3. **In-context Learning**: LangChain 활용 하여 주어진 문서 기반으로 참조하여 대답.

### 5. LangChain 한계 완화
- 정보 접근: Vectorstore, Agent 검색
- 토큰 제한: TextSplitter로 분할
- 할루시네이션: 문서 기반 프롬프팅

### 6. LangChain 요소
1. LLM: 다양한 LLM 사용
2. Prompts: 지시문, 예시 등
3. Index: 문서 탐색 (Document Loader 등)
4. Memory: 대화 기억
5. Chain: 연속 호출 (QnA, Summarization 등)
6. Agents: 복잡한 작업 (Custom Agent)
7. 예시: PDF 챗봇
   1. 문서 업로드, 분할
   2. 임베딩 저장 및 검색
   3. QA Chain: 질문 -> GPT 대답