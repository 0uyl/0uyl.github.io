---
title: Gas 깊이있게 다루기
published: 2025-08-31
tags: [Blockchain, Smartcontract]
category: Blockchain
description: can gas in-depth like this?
draft: false
---

# 1. 단위

- 1 Gwei = 1,000,000,000 Wei (10⁹ Wei)

- 1 ETH = 1,000,000,000 Gwei (10⁹ Gwei)<br><br>

# 2. 가스란?

- Gas = 트랜잭션을 실행하는데 드는 연산량(복잡도) 단위.

- 가스비(요금) = 그 연산량 1단위당 지불하는 가격.

비용 계산 (EIP-1559)
- 총 수수료 = `gasUsed x effectiveGasPrice`

- `effectiveGasPrice = min(maxFeePerGas, baseFee + priorityFee)`
    - **baseFee**(기본 수수료): 블록 혼잡도에 따라 자동 조정, 전량 소각(burn).
    - **priorityFee**(팁): 검증자/채굴자에게 가는 보상.
    - **maxFeePerGas**: "이 이상은 안 낼래" 하는 상한가(남는 건 환불).<br><br>

# 3. 주요 항목 정리

1. Transaction Fee: 실제로 쓴 가스 x 실제 지불 단가(effective gas price).

2. Gas Limit: 이 트랜잭션이 최대로 쓸 수 있는 가스 한도(사용자 지정 가능).

3. Base Fee: Gwei 기준의 기본 수수료(가스당 가격).
    - 소각됨(EIP-1559).
    - 혼잡도 규칙: 블록이 > 50% 차면 다음 블록 상승, **< 50%**면 하락.

4. **Max Fee (maxFeePerGas)**: 가스당 **최대 지불 의사 가격**.

5. Max Priority Fee: 검증자에게 주는 팁 상한(혼잡 시 올리면 포함 우선순위 uP).

6. Block Confirmations: 트랜잭션이 담긴 블록 뒤로 쌓인 블록 수, 많을수록 되돌릴 가능성 down, 안정성 up<br><br>

# gas 예시

- `gasUsed = 21,000`<br>
- `baseFee = 20 gwei`<br>
- `priorityFee = 2 gwei`<br>
- `maxFeePerGas = 40 gwei`<br>
- `effectiveGasPrice = min(40, 20 + 2) = 22 gwei`

- 총 수수료 = `21,000 x 22 gwei = 462,000 gwei = 0.000462 ETH`
    - 이 중 `21,000 x 20 gwei`는 소각, `21,000 x 2 gwei`는 검증자 팁.
    - 상한(40)과 실제(22)의 차이만큼은 환불.






