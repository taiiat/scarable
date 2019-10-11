### Scalable funding of Bitcoin micropayment channel networks





---
## Introduction　
- micropayment channelの課題

  -スケーラビリティ
  
  -チャネル内で決済できる金額の上限




---


## Channel factory

![alt](mpay2.png)

     ３人が参加し、ペアのペイメントチャネルを作る。
---


## Allocation

![alt](mpay4.png)

       サブチャネルで資金が不足した場合、新しいAllocationを作成
---


##  Leaving a group

payment channel:相手のノードがクラッシュしたりオフラインであると
決済できない



Channel Factoryにおいても応答の無いノードがいると、Allocationへの更新やCommitmentの更新ができなくなる。|

+++

アクティブな参加者で新しい共有アカウントを作る

![alt](mpay6.png) 
      
---

### Combining channel factories
     

![alt](mpay7.png)
      
      グループが大きいほど、ブロックチェーンスペースは節約できる
      (オフチェーン決済の量が増える)
  
+++

### Evaluation
