# LLM 기반 QA 검색 시스템 (Hybrid RAG 구조)
📌  프로젝트는 팀 단위로 진행되었으며, 본 리포지토리에는 개인 작성 파트 위주로 일부 공개하였습니다.

이 프로젝트는 학사요람 JSON 데이터를 기반으로 한 RAG QA 시스템 개발 프로젝트입니다.  
BM25 + chromaDB를 활용한 의미 유사도 검색과 프롬프트 테스트를 통해 응답 품질을 개선하였습니다.  

## 🔧 폴더 구성
📁 vectorDB/ ← 벡터 검색용 DB 구축 및 전처리
├── build_db.py
└── flat_json.py

📁 RAG/ ← Hybrid RAG 검색 시스템 구현
└── hybrid_rag_3.py

📁 prompt/ ← 프롬프트 품질 실험 결과
└── prompt_engineering.xlsx

---

## 🧠 주요 기술 스택

- **Embedding & Retrieval**: KoSimCSE, ChromaDB, BM25, Dense Retrieval  
- **Ranking & Generation**: Cross-Encoder, OpenAI GPT API, RAG 구조  
- **Evaluation**: 정량 + 정성 평가 스크립트 + 프롬프트별 응답 비교 `.xlsx` 기반 시각화

---

## 💡 구현 기능 요약

- 학사요람 JSON 데이터 flatten 및 전처리 → 문서 임베딩 → vectorDB 구축
- 학과 키워드 기반 필터링 + BM25 → dense vector search 결합
- Cross-Encoder 기반 re-ranking 적용
- GPT 응답 품질 실험 (정량 + 정성 평가), 자동 기록 파이프라인
