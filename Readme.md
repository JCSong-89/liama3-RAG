CPU Version의 라마3를 맥으로 구동한다.
프레임워크는 라마 인덱스로 한다.
벡터 데이터베이스의 경우 Qdrant로 한다.
아래의 라이브러리를 먼저 설치 한다.

accelerate==0.29.3
einops==0.7.0
sentence-transformers==2.7.0
transformers==4.39.3
qdrant-client==1.9.0
llama-index==0.10.32
llama-index-agent-openai==0.2.3
llama-index-cli==0.1.12
llama-index-core==0.10.32
llama-index-embeddings-fastembed==0.1.4
llama-index-legacy==0.9.48
llama-index-llms-huggingface==0.1.4
llama-index-vector-stores-qdrant==0.2.8

설치 명령어
pip install -r requirements.txt

벡터 데이터베이스 설치
docker run -p 6333:6333 -p 6334:6334 \
 -v $(pwd)/qdrant_storage:/qdrant/storage:z \
 qdrant/qdrant

Qdrant is now accessible:
REST API: localhost:6333
Web UI: localhost:6333/dashboard
GRPC API: localhost:6334

예제 데이터셋
wget "https://arxiv.org/pdf/1810.04805.pdf" -O Data/arxiv.pdf

참고 소스 코드
https://nayakpplaban.medium.com/build-an-advanced-reranking-rag-system-using-llama-index-llama-3-and-qdrant-a8b8654174bc
s
