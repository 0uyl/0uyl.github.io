---
title: Blockchain and Layer and Roll Up
published: 2025-08-31
tags: [Blockchain, Smartcontract]
category: Blockchain
description: Layer and Roll UP
draft: false
---

# 1. 소개 (Introduction)

- 이번 과정에서는 Layer 1, Layer 2, Rollup 같은 개념을 다룸.

# 2. 블록체인 레이어 (Blockchain Layers)
<br>

## Layer 1

- 블록체인의 기본 레이어

- 노드들이 합의를 이루는 핵심 네트워크

- 별도의 확장 기능 없이 
단독으로 작동.

- 예시: 비트코인, 이더리움, 
BNB 체인, 솔라나, 아발란체

- L1 위에 직접 배포된 앱(예: 유니스왑)은 L2가 아니라, L1 위의 dApp임.<br>

## Layer 2

- L1 블록체인 위에서 동작하면서, 다시 L1에 연결되는 확장 레이어.

- 다양한 형태가 있음:
    - Chainlink -> 탈중앙 오라클 네트워크

    - The Graph -> 이벤트 인덱싱 네트워크 (온체인 데이터 접근 지원)

- 가장 중요한 L2 = Rollup<br><br>

# 3. 롤업 (Rollups)
<br>
## 개념

- 이더리움 확장 솔루션 -> 여러 트랜잭션을 묶어서 하나로 압축 후 L1에 기록.<br>

## 블록체인 트릴레마

- 블록체인은 동시에 3가지 특성을 다 갖기 어려움
    1. 탈중앙화 (Decentralization)

    2. 보안(Security)
    
    3. 확장성(Scalability)

-  이더리움은 탈중앙화와 보안을 우선시 -> 확장성은 낮음

- Rollup은 확장성을 보완하면서, 보안과 탈중앙화를 유지하는 솔루션임<br><br>

# 4. 롤업의 작동 방식

1. 사용자가 트랜잭션 제출

2. 오퍼레이터(operator)가 수집 -> 다른 트랜잭션들과 묶어 압축

3. 압축된 번들(batch)을 L1(이더리움)에 제출

4. 가스비는 묶인 모든 사용자끼리 분담<br><br>

# 5. 롤업의 종류
<br>

## Optimistic Rollups
- 모든 오프체인 거래가 유효하다고 가정.

- 오퍼레이터가 새로운 state를 제안 -> 도전 기간(Challenge Period) 동안 다른 검증자가 이의 제기 가능.

- Fraud Proof (사기 증명) 과정:

    - 양쪽 오퍼레이터가 상호 검증 -> 특히 연산 단계만 L1에서 실행에 결과 비교.
    
    - 잘못된 거래면 -> 다시 전체 배치를 재실행.

    - 거짓 거래를 포함한 오퍼레이터는 스테이킹 토큰 몰수(Slashing)<br>

## Zero-Knowledge (ZK) Rollups (영지식)

- 겨래 유효성을 zk-proof(영지식 증명)으로 증명.

- Prover(제공자) -> zk-proof 생성

- Verifier(L1 컨트랙트) -> 증명 검증

- 이때 witness(증인) = 입력값이 해당 수학적 조건을 만족한다는 것을 증명하는 데 사용되는 해<br><br>

# 결론
- 롤업은 이더리움의 확장성을 강화

- 거래를 오프체인에서 처리 -> 묶어서 L1에 기록 -> 보안, 탈중앙화 유지하면서 처리량 향상.









