---
title: Sequencer of Blockchain
published: 2025-08-31
tags: [Blockchain, Smartcontract]
category: Blockchain
description: sort transaction
draft: false
---

# 1. 소개

- 블록체인과 암호화폐 네트워크에서 시퀀서는 트랜잭션을 정렬하고 묶는 역할을 하는 운영자.

-특히 롤업(Rollup) 솔루션에서 시퀀서는 중요한데, 많은 경우 중앙화된 단일 운영자에 의해 관리됨.<br><br>

# 2. 중앙화 리스크 (Centralization Risks)
<br>

## 검열 및 조작

- 중앙화된 시퀀서는 특정 트랜잭션을 선택적으로 차단하거나 지연시킬 수 있음.

- 예로 출금 트랜잭션을 막아 사용자가 자금을 찾지 못하게 하는 상황이 있음

- 또한 거래 순서를 조작해서 개인적 이익을 취할 수 있음 (MEV, front-running 같은 문제)

## 운영 중단

- 중앙화된 시퀀서가 다운되면 -> 모든 트랜잭션 처리 중단.

- 출금 포함 어떤 거래도 처리 불가 -> 시퀀서가 복구될 때까지 네트웤 ㅡ멈춤.<br><br>

# 3. 해결책 

- zkSync 같은 프로젝트는 이러한 문제를 완화하기 위해 시퀀서의 탈중앙화를 추진 중.

- 단일 운영자가 아니라 여러 노드나 여러 주체가 함께 운영하도록 설계


