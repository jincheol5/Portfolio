### ☕️ Research
#### TR-GNN: Temporal Graph 내 도달 가능성(Temporal Reachability) 예측 모델 
> 연구 배경:
> - 불완전하고 노이즈가 존재하는 실세계 데이터에서도 Temporal Graph 내의 Temporal Reachability를 예측할 수 있도록 GNN 기반 예측 모델 연구.
> - 기존의 Temporal GNN 모델들은 두 노드 사이의 hop 수가 증가할수록 예측 성능이 급격히 저하되는 한계 존재.
> - Source 중심의 학습으로 이를 개선할 수 있으나, 새로운 그래프 또는 source에 대한 반복적인 재학습이 필요할 수 있어 일반화 성능 확보 필요.
> 
> 제안 방법:
> - 각 노드의 임베딩이 특정 source를 중심으로 Temporal Reachability 판단에 필요한 정보를 표현하도록 source-dependent GNN 설계.
> - Temporal Reachability 계산 알고리즘의 원리를 학습할 수 있도록 Neural Execution을 적용하여 모델이 정보 전파 과정의 알고리즘적 규칙을 학습하도록 설계.
> 
> 결과:
> - GNN 기반의 Temporal Reachability 예측 모델 TR-GNN 개발.
> - 기존 모델 대비 학습되지 않은 규모의 7-type Temporal Graph 데이터셋에 대한 일반화 성능 약 13% 향상.
> - 새로운 그래프에 대해 반복적인 재학습 없이 도달 가능성을 예측할 수 있는 모델 개발.
>
> Github: [TR-GNN](https://github.com/jincheol5/TR-GNN)

#### TPVis: Temporal Graph 내 정보흐름(Temporal Path) 시각화 시스템 
> 연구 배경:
> - Temporal Graph 내에서 정보흐름을 나타내는 Temporal Path를 직관적으로 분석할 수 있는 시각화 기법 연구.
> - 기존의 Temporal Graph 시각화 기법들은 Graph의 전체적인 변화 표현에 초점을 맞췄기 때문에 그 안의 Temporal Path 인식이 어려움. 
> - Timeline-based Layout인 Linearized-bipartite Layout은 기존 시각화 기법들 중 가장 직관적으로 Temporal Path 시각화 가능하나, 여전히 인식을 방해하는 시각적 혼란 요소들이 발생.
>    
> 제안 방법:
> - 불필요한 시각적 요소들을 제거하기 위해 Temporal Graph 내에서 Temporal Path만을 도출하여 시각화하도록 설계.
> - Linearized-bipartite Layout에서 Temporal Path 인식을 방해하는 3가지 시각적 혼란 요소 정의.
> - Tree Layout 적용을 통해 3가지 시각적 혼란 요소들을 100% 제거하기 위한 Path-to-Tree 변환 프로세스 설계.
> - 정보 전파의 시간적 순서를 효과적으로 표현하기 위한 Timeline-based Layout 설계.
>   
> 결과:
> - Temporal Graph 내의 직관적인 정보흐름 분석을 지원하는 Temporal Path 시각화 시스템 TPVis 개발.
> - SNAP Temporal Graph 데이터셋에 대한 Case Study를 통해 시각적 혼란 요소들 100% 제거 검증.
>   
> Github: [TPVis](https://github.com/jincheol5/TPVis)

<br>

### ☕️ LLM 활용 Project
#### Food_Info_ETL: LLM 기반 식품 이미지 내 영양성분 정보 ETL 자동화 파이프라인
> 개발 배경:
> - 기존에는 서비스 제공에 필요한 식품 정보 DB 구축을 위해 식품 이미지 내의 영양성분 정보를 직접 확인하여 DB에 입력하는 수작업 방식으로 업무 수행.
> - 반복적인 데이터 입력 업무에 대한 부담과 처리 속도의 한계 존재.
>   
> 개발 방법:
> - 이미지 내 정보 추출에 적합한 모델 선정을 위해 DeepSeek, Qwen, Gemma 등 오픈소스 멀티모달 LLM 비교 및 분석하여 Qwen3.5 선정.
> - 이미지 로드 → 영양성분 정보 추출 → 추출 결과 검증 → DB 적재로 구성된 식품 영양성분 정보 ETL 자동화 파이프라인 설계.
> - LangChain을 활용하여 LLM 기반 식품 영양성분 정보 ETL 자동화 파이프라인 구현.
>
> 결과:
> - LLM 기반의 업무 프로세스 자동화 파이프라인 개발.
> - 반복적인 데이터 입력에 소요되는 업무 부담 감소.
> - 기존 수작업 대비 식품 정보 입력 속도 5.33배 향상.
>   
> Github: [Food_Info_ETL](https://github.com/jincheol5/Food_Info_ETL)

#### Chat_EPCIS: LLM 기반 대화형 공급망 국제 표준 GS1 EPCIS 데이터 플랫폼
> 개발 배경:
> - 이전에 연구과제를 수행하며 개발한 공급망 국제표준 GS1 EPCIS 기반 데이터 플랫폼의 제품 이력 추적 성능과 사용성 개선을 목표로 플랫폼 고도화.
> - EPCIS 표준에 따라 공급망 이벤트 단위 데이터 저장 구조로 인해 제품 이력 추적 시 여러 이벤트를 반복적으로 조회해야 하며, 데이터 규모 증가에 따라 처리 속도가 저하되는 문제 존재.
> - 사용자가 데이터를 조회하기 위해 복잡한 EPCIS Query 방식을 이해하고 직접 작성해야 하는 사용성의 한계 존재.
>
> 개발 방법:
> - EPCIS 이벤트 내 제품의 집계·변환·위치 등의 관계를 나타내는 그래프로 모델링.
> - 모델링한 그래프를 Neo4j에 저장·관리하도록 기존 데이터 플랫폼을 확장하고, 단일 Cypher Query로 제품 간 관계를 탐색할 수 있도록 이력 추적 방식 개선.
> - 자연어를 통한 데이터 조회를 지원하기 위해 오픈소스 LLM인 Gemma4 기반의 대화형 Query Agent 설계.
> - 데이터 플랫폼의 조회 기능을 Tool로 정의하고, LangGraph를 활용하여 사용자의 요청에 따라 적절한 Tool을 선택해 필요한 데이터를 조회·응답하는 Tool-RAG 구조의 Query Agent 구현.
>
> 결과:
> - LLM 기반의 대화형 데이터 플랫폼 개발.
> - 반복적인 이벤트 조회를 단일 Cypher Query 기반의 그래프 탐색으로 개선하여 EPCIS 데이터셋에서의 제품 이력 추적 속도 약 16.77배 향상.
> - 사용자가 EPCIS Query 방식에 대한 별도의 이해 없이 자연어만으로 데이터를 조회할 수 있도록 데이터 플랫폼 사용성 개선.
>   
> Github: [Chat_EPCIS](https://github.com/jincheol5/Chat_EPCIS)

<br>

### ☕️ Paper Implementation
#### Graph Algorithm
> ChronoGraph: Enabling temporal graph traversals for efficient information diffusion analysis over time
> 
> Enabling time-centric computation for efficient temporal graph traversals from multiple sources 
> 
> Temporal graph traversals: Definitions, algorithms, and applications
> 
> Path problems in temporal graphs
>
> Github:
>   - All Implementation Github: [TR-GNN](https://github.com/jincheol5/TR-GNN), [TPVis](https://github.com/jincheol5/TPVis), [TR_Embedding](https://github.com/jincheol5/TR_Embedding)

#### Graph Neural Networks
> Graph Attention Networks (GAT)
>
> CircuitNet: An Open-Source Dataset for Machine Learning in VLSI CAD Applications with Improved Domain-Specific Evaluation Metric and Learning Strategies (CircuitNet)
> 
> Inductive Representation Learning on Temporal Graphs (TGAT)
> 
> Temporal Graph Networks for Deep Learning on Dynamic Graphs (TGN)
> 
> Towards Better Dynamic Graph Learning: New Architecture and Unified Library (DyGFormer)
> 
> ReaCH-TGN: Contrastive Hop and Time-Aware Temporal Graph Network for Reachability Prediction (ReaCH-TGN)
> 
> Github:
>   - GAT Implementation Github: [GAT](https://github.com/jincheol5/GAT)
>   - CircuitNet Implementation Github: [CircuitNet](https://github.com/jincheol5/CircuitNet_GNN) 
>   - TGAT, TGN, DyGFormer Implementation Github: [Temporal_GNN](https://github.com/jincheol5/Temporal_GNN)
>   - ReaCH-TGN Implementation Github: [TR_Embedding](https://github.com/jincheol5/TR_Embedding), [TR-GNN](https://github.com/jincheol5/TR-GNN)

#### Walk-based model
> DeepWalk: Online Learning of Social Representations (DeepWalk)
> 
> Continuous-Time Dynamic Network Embeddings (CTDNE)
> 
> A Structure Similarity Based Adaptive Sampling Method for Time-Dependent Graph Embedding (ATDGEB)
> 
> Github:
>   - DeepWalk Implementation Github: [DeepWalk](https://github.com/jincheol5/DeepWalk)
>   - CTDNE, ATDGEB Implementation Github: [Temporal_Walk](https://github.com/jincheol5/Temporal_Walk)

#### Neural Execution 
> Neural Execution of Graph Algorithms (NGAE)
> 
> The CLRS Algorithmic Reasoning Benchmark (CLRS)
>
> Github:
>   - All Implementation Github: [Neural_Execution](https://github.com/jincheol5/Neural_Execution)

#### Graph Visualization
> An Algorithm for Drawing General Undirected Graphs (Kamada-Kawai)
>
> Parallel edge splatting for scalable dynamic graph visualization (Linearized-bipartite)
>
> Github:
>   - Kamada-Kawai Implementation Github: [Kamada-Kawai](https://github.com/jincheol5/kamada_kawai)
>   - Linearized-bipartite Implementation Github: [TPVis](https://github.com/jincheol5/TPVis)





